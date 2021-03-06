---
title: "生成过程中的代码生成 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, build tasks
- text templates, transforming by using msbuild
ms.assetid: 4da43429-2a11-4d7e-b2e0-9e4af7033b5a
caps.latest.revision: "28"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 70200da27d102f0ec6b8231a680965e8ee420d44
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="code-generation-in-a-build-process"></a>生成过程中的代码生成
[文本转换](../modeling/code-generation-and-t4-text-templates.md)可以作为的一部分调用[生成过程](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)的[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]解决方案。 有一些专用于文本转换的生成任务。 T4 生成任务运行设计时文本模板，它们还编译运行时（已预处理的）文本模板。  
  
 根据你使用的引擎，生成任务可完成的操作之间是有一些差异的。 如果文本模板生成 Visual Studio 中的解决方案时，可以访问 Visual Studio API (EnvDTE) [hostspecific ="true"](../modeling/t4-template-directive.md)属性设置。 但当你构建解决方案从命令行或在启动服务器生成通过 Visual Studio 时，就不一样。 在这些情况下，生成由 MSBuild 执行，并且使用不同的 T4 主机。  
  
 这意味着，你不能访问等项目文件的名称相同的方式生成 MSBuild 中的文本模板时。 但是，你可以[通过生成参数，将环境信息传递到文本模板和指令处理器](#parameters)。  
  
##  <a name="buildserver"></a>配置计算机  
 若要启用你的开发计算机上的生成任务，安装 Visual Studio 的建模 SDK。
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

 如果[生成服务器](http://msdn.microsoft.com/Library/788443c3-0547-452e-959c-4805573813a9)在其上的计算机上运行[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]是未安装，在从你的开发计算机的以下文件复制到生成计算机。 替换的最新版本号 *。  
  
-   $(ProgramFiles)\MSBuild\Microsoft\VisualStudio\v*.0\TextTemplating  
  
    -   Microsoft.VisualStudio.TextTemplating.Sdk.Host.*.0.dll  
  
    -   Microsoft.TextTemplating.Build.Tasks.dll  
  
    -   Microsoft.TextTemplating.targets  
  
-   $(ProgramFiles)\Microsoft Visual Studio *.0\VSSDK\VisualStudioIntegration\Common\Assemblies\v4.0  
  
    -   Microsoft.VisualStudio.TextTemplating.*.0.dll  
  
    -   Microsoft.VisualStudio.TextTemplating.Interfaces.*.0.dll（多个文件）  
  
    -   Microsoft.VisualStudio.TextTemplating.VSHost.*.0.dll  
  
-   $(ProgramFiles)\Microsoft Visual Studio *.0\Common7\IDE\PublicAssemblies\  
  
    -   Microsoft.VisualStudio.TextTemplating.Modeling.*.0.dll  
  
## <a name="to-edit-the-project-file"></a>编辑项目文件  
 你将需要编辑你的项目文件才能在 MSBuild 中配置的一些功能。  
  
 在解决方案资源管理器，选择**卸载**从你的项目的上下文菜单。 这允许你在 XML 编辑器中编辑 .csproj 或 .vbproj 文件。  
  
 完成编辑之后，选择**重新加载**。  
  
## <a name="import-the-text-transformation-targets"></a>导入文本转换目标  
 在 .vbproj 或 .csproj 文件中，查找与下类似的行：  
  
 `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />`  
  
 \- 或 -  
  
 `<Import Project="$(MSBuildToolsPath)\Microsoft.VisualBasic.targets" />`  
  
 在该行之后插入文本模板化导入：  
  
```xml  
<!-- Optionally make the import portable across VS versions -->  
  <PropertyGroup>  
    <!-- Get the Visual Studio version - defaults to 10: -->  
    <VisualStudioVersion Condition="'$(VisualStudioVersion)' == ''">10.0</VisualStudioVersion>  
    <!-- Keep the next element all on one line: -->  
    <VSToolsPath Condition="'$(VSToolsPath)' == ''">$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)</VSToolsPath>  
  </PropertyGroup>  
  
<!-- This is the important line: -->  
  <Import Project="$(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets" />  
```  
  
## <a name="transforming-templates-in-a-build"></a>在生成中转换模板  
 有一些属性你可插入项目文件以控制转换任务：  
  
-   在每次生成开始时运行转换任务：  
  
    ```xml  
    <PropertyGroup>  
        <TransformOnBuild>true</TransformOnBuild>  
    </PropertyGroup>  
    ```  
  
-   例如，覆盖只读文件，因为不会签出这些文件：  
  
    ```xml  
    <PropertyGroup>  
        <OverwriteReadOnlyOutputFiles>true</OverwriteReadOnlyOutputFiles>  
    </PropertyGroup>  
    ```  
  
-   每次转换所有模板：  
  
    ```xml  
    <PropertyGroup>  
        <TransformOutOfDateOnly>false</TransformOutOfDateOnly>  
    </PropertyGroup>  
    ```  
  
     默认情况下，T4 MSBuild 任务将重新生成一个输出文件，前提是它早于其模板文件，或早于所有已包含的文件，或早于之前已由模板读取或已由其使用的指令处理器读取的所有文件。 请注意，这是一个依赖项测试，其功能比 Visual Studio 中的“转换所有模板”命令使用的测试强大得多，后者仅比较模板和输出文件的日期。  
  
 若要在项目中仅执行文本转换，请调用 TransformAll 任务：  
  
 `msbuild myProject.csproj /t:TransformAll`  
  
 转换特定文本模板：  
  
 `msbuild myProject.csproj /t:Transform /p:TransformFile="Template1.tt"`  
  
 你可以在 TransformFile 中使用通配符：  
  
 `msbuild dsl.csproj /t:Transform /p:TransformFile="GeneratedCode\**\*.tt"`  
  
## <a name="source-control"></a>源代码管理  
 没有针对源代码管理系统的特定内置集成。 但是，你可以添加自己的扩展，例如，用于签出和签入生成的文件。默认情况下，文本转换任务将避免覆盖标记为只读的文件，因此当遇到此类文件时，将在 Visual Studio 错误列表中记录错误，并且任务将失败。  
  
 若要指定应覆盖只读文件，请插入此属性：  
  
 `<OverwriteReadOnlyOuputFiles>true</OverwriteReadOnlyOuputFiles>`  
  
 除非自定义后续处理步骤，否则会在覆盖文件时，在错误列表中记录相应的警告。  
  
## <a name="customizing-the-build-process"></a>自定义生成过程  
 文本转换发生在生成过程中的其他任务之前。 你可以通过设置 `$(BeforeTransform)` 属性和 `$(AfterTransform)` 属性来定义在转换前后调用的任务：  
  
```  
<PropertyGroup>  
    <BeforeTransform>CustomPreTransform</BeforeTransform>  
    <AfterTransform>CustomPostTransform</AfterTransform>  
  </PropertyGroup>  
  <Target Name="CustomPreTransform">  
    <Message Text="In CustomPreTransform..." Importance="High" />  
  </Target>  
  <Target Name="CustomPostTransform">  
    <Message Text="In CustomPostTransform..." Importance="High" />  
  </Target>  
```  
  
 在 `AfterTransform` 中，你可以引用文件列表：  
  
-   GeneratedFiles - 由过程写入的文件的列表。 对于覆盖现有只读文件的文件，%(GeneratedFiles.ReadOnlyFileOverwritten) 为 true。 可将这些文件签出源代码管理。  
  
-   NonGeneratedFiles - 未覆盖的只读文件的列表。  
  
 例如，定义任务以签出 GeneratedFiles。  
  
## <a name="outputfilepath-and-outputfilename"></a>OutputFilePath 和 OutputFileName  
 这些属性仅由 MSBuild 使用。 它们不影响 Visual Studio 中的代码生成。 它们将生成的输出文件重定向到不同的文件夹或文件。 目标文件夹必须已存在。  
  
```xml  
<ItemGroup>  
  <None Include="MyTemplate.tt">  
    <Generator>TextTemplatingFileGenerator</Generator>  
    <OutputFilePath>MyFolder</OutputFilePath>  
    <LastGenOutput>MyTemplate.cs</LastGenOutput>  
  </None>  
</ItemGroup>  
```  
  
 要重定向到的一个有用的文件夹是 `$(IntermediateOutputPath).`  
  
 如果指定和输出文件名，则它将优先于在模板的输出指令中指定的扩展。  
  
```xml  
<ItemGroup>  
  <None Include="MyTemplate.tt">  
    <Generator>TextTemplatingFileGenerator</Generator>  
    <OutputFileName>MyOutputFileName.cs</OutputFileName>  
    <LastGenOutput>MyTemplate.cs</LastGenOutput>  
  </None>  
</ItemGroup>  
```  
  
 如果您要还变换 VS 使用全部转换，或运行单个文件生成器内的模板，不建议指定 OutputFileName 或 OutputFilePath。 你最终将得到不同的文件路径，具体取决于你触发转换的方式。 这可能很容易让人产生混淆。  
  
## <a name="adding-reference-and-include-paths"></a>添加引用和包括路径  
 主机有一个默认的路径集，主机将在这些路径中搜索模板中引用的程序集。 添加到此路径集：  
  
```  
<ItemGroup>  
    <T4ReferencePath Include="$(VsIdePath)PublicAssemblies\" />  
    <!-- Add more T4ReferencePath items here -->  
</ItemGroup>  
```  
  
 若要设置将在其中搜索包含文件的文件夹，请提供以分号分隔的列表。 通常将添加到现有文件夹列表。  
  
```  
<PropertyGroup>  
    <IncludeFolders>  
$(IncludeFolders);$(MSBuildProjectDirectory)\Include;AnotherFolder;And\Another</IncludeFolders>  
</PropertyGroup>  
  
```  
  
##  <a name="parameters"></a>将生成上下文数据传递到模板  
 你可以在项目文件中设置参数值。 例如，可以传递[生成](../msbuild/msbuild-properties.md)属性和[环境变量](../msbuild/how-to-use-environment-variables-in-a-build.md):  
  
```xml  
<ItemGroup>  
  <T4ParameterValues Include="ProjectFolder">  
    <Value>$(ProjectDir)</Value>  
    <Visible>false</Visible>  
  </T4ParameterValues>  
</ItemGroup>  
```  
  
 在文本模板的 Template 指令中设置 `hostspecific`。 使用[参数](../modeling/t4-parameter-directive.md)指令获取值：  
  
```  
<#@template language="c#" hostspecific="true"#>  
<#@ parameter type="System.String" name="ProjectFolder" #>  
The project folder is: <#= ProjectFolder #>  
  
```  
  
 在指令处理器中，你可以调用 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost.ResolveParameterValue%2A>：  
  
```csharp  
string value = Host.ResolveParameterValue("-", "-", "parameterName");  
```  
  
```vb  
Dim value = Host.ResolveParameterValue("-", "-", "parameterName")  
```  
  
> [!NOTE]
>  仅当你使用 MSBuild 时，`ResolveParameterValue` 才会通过 `T4ParameterValues` 获取数据。 当你使用 Visual Studio 转换模板时，参数将具有默认值。  
  
##  <a name="msbuild"></a>在程序集中使用项目属性和 include 指令  
 MSBuild 中，如 $ （solutiondir） 的 visual Studio 宏不起作用。 你可以改用项目属性。  
  
 编辑 .csproj 或 .vbproj 文件以定义项目属性。 此示例定义一个名为 `myLibFolder` 的属性：  
  
```xml  
<!-- Define a project property, myLibFolder: -->  
<PropertyGroup>  
    <myLibFolder>$(MSBuildProjectDirectory)\..\libs</myLibFolder>  
</PropertyGroup>  
  
<!-- Tell the MSBuild T4 task to make the property available: -->  
<ItemGroup>  
    <T4ParameterValues Include="myLibFolder">  
      <Value>$(myLibFolder)</Value>  
    </T4ParameterValues>  
  </ItemGroup>  
  
```  
  
 现在，你可以在 Assembly 和 Include 指令中使用项目属性：  
  
```  
<#@ assembly name="$(myLibFolder)\MyLib.dll" #>  
<#@ include file="$(myLibFolder)\MyIncludeFile.t4" #>  
```  
  
 这些指令在 MSBuild 和 Visual Studio 主机中都通过 T4parameterValues 获取值。  
  
## <a name="q--a"></a>问题解答  
 **为什么需要在生成服务器中转换模板？我已在我的代码签入前转换 Visual Studio 中的模板。**  
  
 如果你更新一个包含的文件或模板读取的另一个文件，则 Visual Studio 不会自动转换相应文件。 所有内容均转换模板，如生成的一部分可确保是最新。  
  
 **其他还有哪些选项适用于转换文本模板？**  
  
-   [TextTransform 实用工具](../modeling/generating-files-with-the-texttransform-utility.md)可以在命令脚本中使用。 在大多数情况下，很方便地使用 MSBuild。  
  
-   [在 VS 扩展中调用文本转换](../modeling/invoking-text-transformation-in-a-vs-extension.md)  
  
-   [设计时文本模板](../modeling/design-time-code-generation-by-using-t4-text-templates.md)由 Visual Studio 转换。  
  
-   [运行时文本模板](../modeling/run-time-text-generation-with-t4-text-templates.md)转换在运行时在你的应用程序。  
  
## <a name="read-more"></a>阅读详细信息  
 在 T4 MSbuild 模板（位于 $(VSToolsPath)\TextTemplating\Microsoft.TextTemplating.targets）提供了有用的指南  
  
 [编写 T4 文本模板](../modeling/writing-a-t4-text-template.md)  
  
 [Oleg Sych： 了解 T4:MSBuild 集成](http://www.olegsych.com/2010/04/understanding-t4-msbuild-integration/)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

