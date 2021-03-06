---
title: "颜色和样式 for Visual Studio |Microsoft 文档"
ms.custom: 
ms.date: 07/31/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e384ea1-4d9e-4307-8884-6e183900732c
caps.latest.revision: "4"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b6d287e7e85ef908f9504f8e1f66e0c221042553
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
# <a name="colors-and-styling-for-visual-studio"></a>颜色和 Visual Studio 的样式
## <a name="using-color-in-visual-studio"></a>使用 Visual Studio 中的颜色  
在 Visual Studio 中，颜色主要用作通信工具，而不仅仅是作为修饰。 按最小方式使用颜色和保留要在其中的情况下：  
  
-   通信含义或隶属关系 （例如，平台或语言修饰符）  
  
-   吸引注意力 （例如，指示状态更改）  
  
-   改善可读性和导航用户界面提供界标  
  
-   增加愿望  
  
存在多个选项用于将颜色分配到 Visual Studio 中的 UI 元素。 有时可能很难图出哪个选项，就应该使用，或如何正确使用它。 本主题将帮助你：  
  
1.  了解不同的服务以及用于定义在 Visual Studio 中的颜色的系统。  
  
2.  选择了正确的选项为给定元素。  
  
3.  正确地使用你选择的选项。  
  
> **注意：**永远不会进行硬编码十六进制、 RGB 或为你的 UI 元素的系统颜色。 使用本服务允许在优化色调的灵活性。 此外，没有服务，你将不能充分利用的主题切换功能[VSColor 服务](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService)。
  
### <a name="methods-for-assigning-color-to-visual-studio-interface-elements"></a>用于将颜色分配到 Visual Studio 界面元素的方法  
选择最适合你的 UI 元素的方法。  
  
| 你的 UI | 方法 | 它们是什么？ |  
| --- | --- | --- |  
| 具有嵌入或独立对话框。 | **系统颜色** | 允许定义的颜色和外观的 UI 元素中，操作系统的系统名称，如公共对话框控件。 |
| 具有你想要与整体的 VS 环境保持一致的自定义 UI 的 UI 元素的类别和语义含义共享令牌相匹配。 | **公共共享的颜色** | 现有的预定义的颜色标记名称的特定 UI 元素 |
| 你具有的各个功能的组，并且没有用于类似元素无共享的颜色。 | **自定义颜色** | 颜色标记名称，是特定于区域并且不能与其他 UI，共享 |
| 你想要允许最终用户以进行自定义 UI 或内容 （例如，文本编辑器或专用的设计器窗口）。 | **最终用户自定义项**<br /><br />**(工具&gt;选项对话框)** | 定义的"字体和颜色"页中设置**工具&gt;选项**对话框或特定于一个 UI 功能的专用的页面。 |
  
### <a name="visual-studio-themes"></a>Visual Studio 主题  
Visual Studio 功能三种不同的颜色主题： 浅色、 深色，和蓝色。 它还检测高对比度模式，这是系统级颜色主题用于可访问性。  
  
用户会提示您在其首次使用 Visual Studio 的过程中选择一个主题，并可以通过转到更高版本切换主题**工具&gt;选项&gt;环境&gt;常规**并选择从新的主题"颜色主题"下拉菜单。  
  
用户还可以使用控制面板以将其整个系统切换到多个高对比度主题之一。 如果用户选择一个高对比度主题，然后 Visual Studio 颜色主题选择器不会再影响颜色在 Visual Studio 中，虽然任何主题更改会保存，以便在用户退出高对比度模式时。 有关高对比度模式的详细信息，请参阅[选择高对比度颜色](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ChoosingHighContrastColors)。
  
### <a name="the-vscolor-service"></a>VSColor 服务  
Visual Studio 提供的环境颜色服务，称为 VSColor 服务，该对话框可以将你的 UI 元素的颜色值绑定到命名的条目，其中包含每个 Visual Studio 主题的颜色值。 这可确保您的颜色将自动更改，以反映当前用户所选主题或系统高对比度模式。 使用服务意味着在一个位置进行处理的所有主题相关的颜色更改的实现，并且如果你使用的从服务的公共共享的颜色，你的 UI 将会自动反映在将来版本的 Visual Studio 中的新主题。  
  
### <a name="implementation"></a>实现  
Visual Studio 源代码包括多个包定义文件中包含标记名称和每个主题的各自的颜色值的列表。 颜色服务读取这些包定义文件中定义 VSColors。 在 XAML 标记中或在代码中引用这些颜色，然后加载通过`IVsUIShell5.GetThemedColor`方法或 DynamicResource 映射。  
  
### <a name="system-colors"></a>系统颜色  
默认情况下，公共控件引用系统颜色。 如果您希望你的 UI 使用系统颜色，如当创建嵌入或独立对话框中，你不必执行任何操作。  
  
### <a name="common-shared-colors-in-the-vscolor-service"></a>VSColor 服务中的公共共享的颜色  
界面元素应反映整体的 Visual Studio 环境。 通过重复使用公共共享的颜色适用于您设计用户界面组件，你可以确保你的接口与其他 Visual Studio 接口，一致，并且，当您的颜色主题是添加或更新时，将自动更新。  
  
使用之前公共共享的颜色，请确保你已了解如何正确使用它们。 公共共享颜色的使用不当可能会导致不一致，令人沮丧，或混乱的体验，为你的用户。  
  
### <a name="user-customizable-colors"></a>用户可自定义颜色  
请参阅：[的最终用户公开颜色](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_ExposingColorsForEndUsers)  
  
有时，你将想要允许最终用户创建的代码编辑器或设计图面时像一样自定义你的 UI。 可自定义 UI 组件都位于**字体和颜色**部分**工具&gt;选项**对话框中，用户可以选择要更改的前景色和 / 或背景色。  
  
![工具&gt;选项对话框](../../extensibility/ux-guidelines/media/0301-a_toolsoptionsdialog.png "0301 a_ToolsOptionsDialog")<br />工具&gt;选项对话框
  
##  <a name="BKMK_TheVSColorService"></a>VSColor 服务  
Visual Studio 提供的环境颜色服务，也称为 VSColor 服务或 shell 颜色服务。 此服务，可将你的 UI 元素的颜色值绑定到的名称-值颜色集包含每个主题的颜色。 必须对于所有 UI 元素，使用 VSColor 服务，以便颜色自动改变以反映当前用户所选主题设置，以便 UI 绑定到的环境颜色服务将与和集成新的主题在将来版本的 Visual Studio。  
  
### <a name="how-the-service-works"></a>服务工作原理  
环境颜色服务读取 VSColors 在 UI 组件.pkgdef 中定义。 这些 VSColors 然后引用在 XAML 标记或代码中，并将其加载通过`IVsUIShell5.GetThemedColor`或`DynamicResource`映射。  
  
![环境颜色服务体系结构](../../extensibility/ux-guidelines/media/0302-a_environmentcolorservicearchitecture.png "0302 a_EnvironmentColorServiceArchitecture")<br />环境颜色服务体系结构
  
### <a name="accessing-the-service"></a>访问服务
有多种不同 VSColor 服务，具体取决于哪种类型的颜色标记你正在使用的访问和具有哪种类型的代码。  

#### <a name="predefined-environment-colors"></a>预定义的环境颜色  
  
##### <a name="from-native-code"></a>从本机代码  
Shell 提供服务，提供对`COLORREF`的颜色。 服务/接口是：  
  
```  
IVsUIShell2::GetVSSysColorEx(VSSYSCOLOR dwSysColIndex, DWORD *pdwRGBval)  
```  
  
文件 VSShell80.idl，在枚举中`__VSSYSCOLOREX`具有 shell 颜色常量。 若要使用它，在将作为传递的索引值中的值其中任意一个`enum __VSSYSCOLOREX`中有案可稽的 MSDN 或常规索引号 Windows 系统 API， `GetSysColor`，接受。 执行此操作返回获取应在第二个参数中使用的颜色的 RGB 值。  
  
如果存储的钢笔或画笔用新的颜色，你必须`AdviseBroadcastMessages`（从 Visual Studio shell 中) 和侦听`WM_SYSCOLORCHANGE`和`WM_THEMECHANGED`消息。  
  
  
若要访问本机代码中的颜色服务，你将使类似于此的调用： 

```
pUIShell2->GetVSSysColorEx(VSCOLOR_COLOR_NAME, &rgbLOCAL_COLOR);    
```  

> **注意：** `COLORREF`返回的值`GetVSSysColorEx()`包含刚 R，G，B 组件的主题颜色。 如果主题条目使用透明度，在返回之前的 alpha 通道值将被放弃。 因此，如果需要在其中透明度通道是重要的地方使用感兴趣的环境颜色，则应使用`IVsUIShell5.GetThemedColor`而不是`IVsUIShell2::GetVSSysColorEx`，如本主题后面所述。  
  
##### <a name="from-managed-code"></a>从托管代码  
通过本机代码中访问 VSColor 服务将非常简单。 如果你正在调试托管代码，但是，确定如何使用服务可能会很棘手。 这一点，下面是 C# 代码段演示此过程：  
  
```  
private void VSColorPaint(object sender, System.Windows.Forms.PaintEventArgs e)  
{  
    //getIVSUIShell2  
    IVsUIShell2 uiShell2 = Package.GetService(typeof(SVsUIShell)) as IVsUIShell2;  
    Debug.Assert (uiShell2 != null, "failed to get IVsUIShell2");  
  
    if (uiShell2 != null)  
    {  
        //get the COLORREF structure  
        uint win32Color;  
        uiShell.GetVSSysColorEx(VSSYSCOLOREX.VSCOLOR_SMARTTAG_HOVER_FILL, out win32Color);  
  
        //translate it to a managed Color structure  
        Color myColor = ColorTranslator.FromWin32((int)win32Color);  
        //use it  
        e.Graphics.FillRectangle(new SolidBrush(myColor), 0, 0, 100, 100);  
    }  
}  
```  
  
如果你正在 Visual Basic 中，使用：  
  
```  
Dim myColor As Color = ColorTranslator.FromWin32((Integer)win32Color)  
```  
  
##### <a name="from-wpf-ui"></a>从 WPF UI  
可以绑定到通过导出到应用程序的值的 Visual Studio 颜色`ResourceDictionary`。 下面是使用颜色表中的资源，以及绑定到 XAML 中的环境字体数据的示例。  
  
```  
<Style TargetType="{x:Type Button}">  
    <Setter Property="TextBlock.FontFamily"  
            Value="{DynamicResource VsFont.EnvironmentFontFamily}" />  
    <Setter Property="TextBlock.FontSize"  
            Value="{DynamicResource VsFont.EnvironmentFontSize}" />  
    <Setter Property="Background"  
            Value="{DynamicResource VsBrush.EnvironmentBackgroundGradient}" />  
</Style>  
```  
  
#### <a name="helper-classes-and-methods-for-managed-code"></a>帮助器类和托管代码的方法  
对于托管代码，shell 的托管包框架库 (`Microsoft.VisualStudio.Shell.12.0.dll`) 包含的帮助程序类推进的主题颜色使用几个。  
  
中的帮助器方法`Microsoft.VisualStudio.Shell.VsColors`中 MPF 类包括`GetThemedGDIColor()`和`GetThemedWPFColor()`。 这些帮助器方法返回主题项作为的颜色值`System.Drawing.Color`或`System.Windows.Media.Color`，以在 WinForms 或 WPF UI 中使用。  
  
```  
IVsUIShell5 shell5;  
Button button = new Button();  
button.BackColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemBrushKey);  
button.ForeColor = GetThemedGDIColor(shell5, SolutionExplorerColors.SelectedItemTextBrushKey);  
  
/// <summary>  
/// Gets a System.Drawing.Color value from the current theme for the given color key.  
/// </summary>  
/// <param name="vsUIShell">The IVsUIShell5 service, used to get the color's value.</param>  
/// <param name="themeResourceKey">The key to find the color for.</param>  
/// <returns>The current theme's value of the named color.</returns>  
public static System.Drawing.Color GetThemedGDIColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)  
{  
   Validate.IsNotNull(vsUIShell, "vsUIShell");  
   Validate.IsNotNull(themeResourceKey, "themeResourceKey");  
  
   byte[] colorComponents = GetThemedColorRgba(vsUIShell, themeResourceKey);  
  
   // Note: The Win32 color we get back from IVsUIShell5.GetThemedColor is ABGR  
   return System.Drawing.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]);  
}  
  
private static byte[] GetThemedColorRgba(IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)  
{  
   Guid category = themeResourceKey.Category;  
   __THEMEDCOLORTYPE colorType = __THEMEDCOLORTYPE.TCT_Foreground  
   if (themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundColor || themeResourceKey.KeyType == ThemeResourceKeyType.BackgroundBrush)  
   {  
      colorType = __THEMEDCOLORTYPE.TCT_Background;  
   }  
  
   // This call will throw an exception if the color is not found  
   uint rgbaColor = vsUIShell.GetThemedColor(ref category, themeResourceKey.Name, (uint)colorType);  
   return BitConverter.GetBytes(rgbaColor);  
}  
public static System.Windows.Media.Color GetThemedWPFColor(this IVsUIShell5 vsUIShell, ThemeResourceKey themeResourceKey)  
{  
   Validate.IsNotNull(vsUIShell, "vsUIShell");  
   Validate.IsNotNull(themeResourceKey, "themeResourceKey");  
  
   byte[] colorComponents = GetThemedColorComponents(vsUIShell, themeResourceKey);  
  
    return System.Windows.Media.Color.FromArgb(colorComponents[3], colorComponents[0], colorComponents[1], colorComponents[2]);  
}    
```  
  
类还可以用于获取 VSCOLOR 标识符的给定 WPF 颜色资源键，反之亦然。  
  
```  
public static string GetColorBaseKey(int vsSysColor);  
public static bool TryGetColorIDFromBaseKey(string baseKey, out int vsSysColor);  
```  
  
方法`VsColors`类查询 VSColor 服务以返回每次调用它们的颜色值。 若要获取作为一个颜色值`System.Drawing.Color`，并提高性能的替代方法是改为使用的方法`Microsoft.VisualStudio.PlatformUI.VSThemeColor`类，该类将缓存从 VSColor 服务中获取的颜色值。 类内部订阅 shell 广播的消息事件，并发生主题更改事件时放弃缓存的值。 此外，此类提供。主题更改订阅的 NET 友好事件。 使用`ThemeChanged`事件来添加新的处理程序，并使用`GetThemedColor()`方法来获取颜色值`ThemeResourceKeys`感兴趣。 示例代码可能如下所示：  
  
```  
public MyWindowPanel()  
{  
    InitializeComponent();  
  
    // Subscribe to theme changes events so we can refresh the colors  
    VSColorTheme.ThemeChanged += VSColorTheme_ThemeChanged;  
  
    RefreshColors();  
}  
  
private void VSColorTheme_ThemeChanged(ThemeChangedEventArgs e)  
{  
    RefreshColors();  
  
    // Also post a message to all the children so they can apply the current theme appropriately  
    foreach (System.Windows.Forms.Control child in this.Controls)  
    {  
        NativeMethods.SendMessage(child.Handle, e.Message, IntPtr.Zero, IntPtr.Zero);  
    }  
}  
  
private void RefreshColors()  
{  
    this.BackColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowBackgroundColorKey);  
    this.ForeColor = VSColorTheme.GetThemedColor(EnvironmentColors.ToolWindowTextColorKey);  
}  
  
protected override void Dispose(bool disposing)  
{  
    if (disposing)  
    {  
        VSColorTheme.ThemeChanged -= this.VSColorTheme_ThemeChanged;  
        base.Dispose(disposing);}  
}  
```  
  
##  <a name="BKMK_ChoosingHighContrastColors"></a>选择高对比度颜色  
  
### <a name="overview"></a>概述  
Windows 使用几个增加的文本、 背景和映像，颜色对比度的高对比度系统级主题使元素显示在屏幕上更为明显。 出于可访问性原因，很重要，Visual Studio 界面元素时正确响应用户切换到高对比度主题。  
  
只有少量的系统颜色可以用于高对比度主题。 在选择你的系统颜色名称时，请记住以下提示：  
  
1.  **选择具有相同的语义含义的系统颜色**作为你着色的元素。 例如，如果选择的时间段内的文本的高对比度颜色时，使用 WindowText 和不 ControlText。  
  
2.  **选择前景/背景对**在一起或你将无法确信所有的高对比度主题中，颜色选择将正常工作。  
  
3.  **确定你的 UI 中的哪些部分是最重要，并确保内容区域将突出。**你将丢失大量的详细信息，通常将区分颜色色调存在一些细微差别，因此强边框颜色的使用是常见定义的内容区域，因为有不同的内容区域没有颜色变体。  
  
### <a name="system-color-set"></a>系统颜色设置  
在表[WPF 团队博客： SystemColors 引用](http://blogs.msdn.com/b/wpf/archive/2010/11/30/systemcolors-reference.aspx)指示组完整的系统颜色名称和相应的色调显示在每个主题。  
  
在将这些知识有限的一组颜色到你的 UI，*应，则将会失去细微"正常"主题中的详细信息*。 此处是一个用于区分工具窗口内的区域的细微灰颜色 UI。 当与在高对比度模式中显示的相同窗口配对，你可看到所有背景都是相同的色调和由单独的边框指示的那些区域的边框：  
  
![在高对比度会丢失的如何细微的详细信息示例](../../extensibility/ux-guidelines/media/030303-a_propertieswindow.png "030303 a_PropertiesWindow")<br />在高对比度会丢失的如何细微的详细信息示例
  
#### <a name="choosing-text-colors-in-an-editor"></a>在编辑器中选择文本颜色  
在编辑器中或设计图面上使用以的文本，以指示含义，例如允许以方便地识别相似的项目组。 高对比度主题中，但是，你没有能够区分多个三种文本颜色。 WindowText、 GrayText 和 HotTrackText 是 WindowBackground 曲面上可用的唯一颜色。 由于你无法使用三个以上的颜色，请仔细选择你想要在高对比度模式中显示的最重要差异。  
  
为每个要与出现在每个高对比度主题编辑器在面上，允许的标记名称的色调：  
  
![高对比度编辑器比较](../../extensibility/ux-guidelines/media/030303-b_hceditorcomparison.png "030303 b_HCEditorComparison")<br />高对比度编辑器比较
  
蓝色主题中的编辑器面的示例：  
  
![蓝色主题中的编辑器](../../extensibility/ux-guidelines/media/030303-c_editorblue.png "030303 c_EditorBlue")<br />蓝色主题中的编辑器
  
![高对比度 #1 主题中的编辑器](../../extensibility/ux-guidelines/media/030303-d_editorhc1.png "030303 d_EditorHC1")<br />高对比度 #1 主题中的编辑器
  
### <a name="usage-patterns"></a>使用模式
许多常见的 UI 元素已定义的高对比度颜色。 因此，UI 元素与类似组件一致，都可以选择自己的系统颜色名称时引用这些使用模式。  
  
| 系统颜色 | 用法 |
| --- | --- |
| ActiveCaption | -Active IDE 和 rafted 的窗口按钮上悬停和已按下标志符号<br />IDE 和 rafted 的窗口的标题栏背景<br />默认状态栏背景 |
| ActiveCaptionText | -Active IDE 和 rafted 的窗口标题栏前景 （文本和标志符号）<br />-背景和边框上悬停和已按活动窗口按钮 |
| 控件 | -组合框、 下拉列表中，搜索控件默认和禁用背景信息，包括下拉按钮<br />形式停靠目标按钮背景<br />命令栏背景<br />工具窗口背景 |
| ControlDark | -IDE 背景<br />菜单和命令栏分隔符<br />命令栏边框<br />菜单阴影<br />-工具窗口选项卡上的默认和悬停边框和分隔符<br />-很好地文档溢出按钮背景<br />形式停靠目标标志符号边框 |
| ControlDarkDark |-失去焦点的选定文档选项卡窗口 |
| ControlLight |-自动隐藏选项卡边框<br />-组合框和下拉列表边框<br />-停靠目标背景和边框 |
| ControlLightLight | -已选定、 已设定焦点的临时边框 |
| ControlText | -组合框和下拉列表标志符号<br />工具窗口未选定的选项卡文本 |
| GrayText |的禁用边框、 下拉列表标志符号、 文本和菜单项文本组合框和下拉列表<br />-已禁用的菜单文本<br />搜索控件搜索选项标头文本<br />搜索控件部分分隔符 |
| 突出显示 | -所有悬停和已按下的背景和边框、 除组合框下拉按钮背景和文档以及溢出按钮边框<br />-所选项背景 |
| HighlightText | -所有悬停和已按下的前景具有 （文本和标志符号）<br />-已设定焦点的工具窗口和文档选项卡窗口控件的前景<br />-已设定焦点的工具窗口标题栏边框<br />-已设定焦点、 与选定的临时选项卡前景<br />悬停和已按上的文档以及溢出按钮边框<br />-所选图标边框|
| HotTrack | -滚动条滚动块背景和边框上按<br />-滚动条上按箭头标志符号 |
| InactiveCaption | 非活动 IDE 和 rafted 的窗口按钮悬停时的标志符号<br />IDE 和 rafted 的窗口的标题栏背景<br />-已禁用的搜索控件背景 |
| InactiveCaptionText | 非活动 IDE 和 rafted 的 windows 标题栏前景 （文本和标志符号）<br />非活动窗口按钮背景和上悬停时的边框<br />-失去焦点的工具窗口按钮背景和边框<br />-已禁用的搜索控件的前景 |
| 菜单 | -下拉列表菜单背景<br />校验和的禁用的复选标记背景 |
| MenuText | -下拉列表菜单边框<br />-选中标记<br />菜单标志符号<br />-下拉列表菜单文本<br />-所选图标边框 |  
| Scrollbar | -滚动栏和滚动条箭头背景，所有状态 |
| 窗口 | -自动隐藏选项卡背景<br />菜单栏和命令架背景<br />-失去焦点或未选定的文档窗口选项卡背景和文档边框，打开和临时选项卡<br />-失去焦点的工具窗口标题栏背景<br />工具窗口选项卡背景，同时选中和取消选中 |
| WindowFrame | -IDE 边框 |
| WindowText | -自动隐藏选项卡前景<br />-所选的工具窗口选项卡前景<br />-失去焦点或未选定的临时选项卡前景色和失去焦点的文档窗口选项卡<br />-未选定标志符号通过树视图默认前景色和悬停<br />工具窗口选定的选项卡边框<br />-滚动条滚动块背景、 边框和标志符号 |
  
##  <a name="BKMK_ExposingColorsForEndUsers"></a>为最终用户公开颜色  
  
### <a name="overview"></a>概述  
有时你将想要允许最终用户在创建代码编辑器中或设计图面时像一样自定义你的 UI。 若要执行此操作的最常见方法是使用**工具&gt;选项**对话框。 除非您具有高度的专用需要特殊控件的 UI，以提供自定义项的最简单方法是通过**字体和颜色**页内**环境**对话框部分。 对于公开的自定义每个元素，用户可以选择更改的前景色和 / 或背景色。

### <a name="building-a-vspackage-for-your-customizable-colors"></a>生成可自定义颜色的 VSPackage  
VSPackage 可以控制的字体和颜色通过自定义类别和项显示在字体和颜色属性页。 当使用此机制，Vspackage 必须实现[IVsFontAndColorDefaultsProvider](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.aspx)接口和其关联的接口。  
  
原则上，此机制可以用于修改所有现有的显示项和包含它们的类别。 但是，它不应修改的文本编辑器类别或其显示项。 文本编辑器类别的详细信息，请参阅[字体和颜色概述](../font-and-color-overview.md)。  
  
若要实现自定义类别或显示项，VSPackage 必须：  
  
-   **创建或标识注册表中的类别。** IDE 实现**字体和颜色**属性页使用此信息来正确查询支持给定的类别中的服务。  
  
-   **创建或标识注册表 （可选） 中的组。** 它可能会很有用定义组中，这表示两个或多个类别的并集。 如果定义一个组，则 IDE 将自动合并子类别，并将分发组内的显示项。  
  
-   **实现 IDE 支持。**  
  
-   **处理字体和颜色的更改。**  
  
#### <a name="to-create-or-identify-categories"></a>若要创建或标识类别  
构造一个特殊类型的类别下的注册表项`[HKLM\SOFTWARE\Microsoft \Visual Studio\\<Visual Studio version\>\FontAndColors\\<Category\>]`其中`<Category>`是类别的非本地化名称。
  
填充具有两个值注册表：  

| 名称 | 类型 | 数据 | 描述 |
| --- | --- | --- | --- |
| 类别 | REG_SZ | GUID | 一个 GUID 创建来标识类别 |
| Package | REG_SZ | GUID | 支持类别 VSPackage 服务的 GUID |
  
 在注册表中指定的服务必须提供的一个实现[IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx)为相应的类别。  
  
#### <a name="to-create-or-identify-groups"></a>若要创建或标识组  
构造一个特殊类型的类别下的注册表项`[HKLM\SOFTWARE\Microsoft \Visual Studio\\<Visual Studio version\>\FontAndColors\\<group\>]`其中`<group>`是组的非本地化名称。  
  
填充具有两个值注册表：

| 名称 | 类型 | 数据 | 描述 |
|--- | --- | --- | --- |
| 类别 | REG_SZ | GUID | 一个 GUID 创建来标识类别 |
| Package | REG_SZ | GUID | 支持类别 VSPackage 服务的 GUID |
  
在注册表中指定的服务必须提供的一个实现`T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup`为相应的组。

![实现 IVsFontAndColorGroup](../../extensibility/ux-guidelines/media/0304-a_fontandcolorgroup.png "0304 a_FontAndColorGroup")<br />实现`IVsFontAndColorGroup`
  
### <a name="to-implement-ide-support"></a>若要实现 IDE 支持  
实现[GetObject](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaultsprovider.getobject.aspx)，其返回[IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx)接口或`T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup`接口为每个类别 IDE 或组提供的 GUID。  
  
为它支持每个类别，VSPackage 实现的单独实例[IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx)接口。  
  
方法通过实现[IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx)必须提供具有的 IDE:  
  
-   类别中的显示项列表  
  
-   可本地化的显示项的名称  
  
-   显示类别的每个成员的信息  
  
 > **注意：**每个类别必须包含至少一个显示项。
  
IDE 使用`T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup`接口可定义的几个类别的联合。

其实现提供具有的 IDE:

-   构成了一组给定类别的列表  
  
-   实例的访问[IVsFontAndColorDefaults](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolordefaults.aspx)支持组内的每个类别  
  
-   可本地化的组名称  
  
#### <a name="updating-the-ide"></a>更新 IDE  
IDE 缓存字体和颜色设置的信息。 因此，IDE 字体和颜色配置任何修改，确保缓存最新后一种最佳做法。  
  
更新缓存通过[IvsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx)接口，并可以执行的全局或仅在所选的项目。  
  
### <a name="handling-font-and-color-changes"></a>处理字体和颜色的更改  
若要正确支持 VSPackage 显示的文本的着色，支持 VSPackage 的着色服务必须响应通过字体和颜色的属性页所做的用户启动的更改。  
  
若要执行此操作，VSPackage 必须：  
  
-   **处理 IDE 生成的事件**通过实现[IVsFontAndColorEvents](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.aspx)接口。 IDE 调用相应方法后面的字体和颜色页上的用户修改。 例如，它调用[OnFontChanged](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorevents.onfontchanged.aspx)方法如果选择新的字体。  
  
 **OR**  
  
-   **轮询更改 IDE**。 这可以通过系统实现[IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx)接口。 主要用于支持持久性，尽管[GetItem](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.getitem.aspx)方法可以获取显示项的字体和颜色信息。 字体和颜色设置的详细信息，请参阅 MSDN 文章[访问存储的字体和颜色设置](../accessing-stored-font-and-color-settings.md)。  
  
> **注意：**若要确保轮询结果正确无误，请使用[IVsFontAndColorCacheManager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorcachemanager.aspx)接口来确定缓存刷新和更新是否需要在调用的检索方法之前[IVsFontAndColorStorage](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivsfontandcolorstorage.aspx)接口。
  
#### <a name="registering-custom-font-and-color-category-without-implementing-interfaces"></a>注册自定义字体和颜色类别，无需实现接口  
下面的代码示例演示如何注册自定义字体和颜色而无需实现接口的类别：  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\FontAndColors\CSharp Tool Window]  
"Package"="{F5E7E71D-1401-11D1-883B-0000F87579D2}"  
"Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}"  
"ToolWindowPackage"="{7259e420-6241-4e0d-b535-5b820671d183}"  
  
    "NameID"=dword:00000064  
```  

此代码示例：   
-   `"NameID"`= 在包中的本地化的类别名称的资源 ID
-   `"ToolWindowPackage"`= 包 GUID
-   `"Category"="{9FF46859-A47E-47bf-8AC5-EC3DBE69D1FE}"`只是一个示例和实际值可以是新提供的实施者的 GUID。  
  
### <a name="set-the-font-and-color-property-category-guid"></a>设置字体和颜色属性类别 GUID  
下面的代码示例演示如何设置类别的 Guid。  
  
```  
// m_pView is your IVsTextView  
IVsTextEditorPropertyCategoryContainer spPropCatContainer =  
(IVsTextEditorPropertyCategoryContainer)m_pView;  
if (spPropCatContainer != null)  
{  
IVsTextEditorPropertyContainer spPropContainer;  
Guid GUID_EditPropCategory_View_MasterSettings =  
new Guid("{D1756E7C-B7FD-49a8-B48E-87B14A55655A}");  
hr = spPropCatContainer.GetPropertyCategory(  
ref GUID_EditPropCategory_View_MasterSettings,  
out spPropContainer);  
if(hr == 0)  
{  
hr =  
spPropContainer.SetProperty(  
VSEDITPROPID.VSEDITPROPID_ViewGeneral_FontCategory,  
catGUID);  
hr =  
spPropContainer.SetProperty(  
VSEDITPROPID.VSEDITPROPID_ViewGeneral_ColorCategory,  
catGUID);  
}  
}  
```  
