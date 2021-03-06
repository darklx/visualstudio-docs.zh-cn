---
title: "了解如何使用 Visual Studio 2017 中的 Live Unit Testing 测试代码 | Microsoft Docs | Microsoft Docs"
ms.date: 2017-08-31
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83458b769b5551ed07774e244cce65a97477a713
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="get-started-with-live-unit-testing-in-visual-studio"></a>Visual Studio 中的 Live Unit Testing 入门

在 Visual Studio 解决方案中启用 Live Unit Testing 后，Live Unit Testing 可以直观描述测试覆盖率和测试状态。 每当修改代码时，它还可以动态执行测试。 当更改破坏了代码并指示其他测试所需的区域时，它会立即发送通知。 

Live Unit Testing 可用于测试针对 .NET Framework 或 .NET Core 的解决方案。 本教程将通过创建面向 .NET Standard 的简单类库来说明 Live Unit Testing 的用法，并创建面向 .NET Core 的 MSTest 项目来对其进行测试。

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
可从 GitHub 上的 [MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/csharp/UtilityLibraries/) 存储库下载完整的 C# 解决方案。
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
可从 GitHub 上的 [MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/visual-basic/UtilityLibraries/) 存储库下载完整的 Visual Basic 解决方案。

---

## <a name="prerequisites"></a>先决条件

本教程需要已安装具有 .NET Core 2.0 工作负载的 Visual Studio 2017 Enterprise Edition 版本 15.3。

## <a name="create-the-solution-and-the-class-library-project"></a>创建解决方案和类库项目

首先，创建名为 `UtilityLibraries` 的 Visual Studio 解决方案，其中包含单个 .NET Standard 类库项目 `StringLibrary`。 可以使用 C# 或 Visual Basic 编写 `StringLibrary`。 

解决方案只是一个可以存储一个或多个项目的容器。 要创建解决方案，请打开 Visual Studio 2017 并执行以下操作：

1. 从顶级的 Visual Studio 菜单中依次选择“文件”、“新建”、“项目”。

1. 在“新建项目”对话框中，展开“其他项目类型”节点，然后选择“Visual Studio 解决方案”。 在右窗格中选择“空白解决方案”，然后在“名称”文本框中输入 `UtilityLibraries`，如下图所示：

   ![“新建项目”对话框](./media/lut-start/new-solution.png)

1. 选择“确定”创建解决方案。
 
现在已创建解决方案，接下来需要创建一个名为 `StringLibrary` 的类库，其中包含大量用于处理字符串的扩展方法。

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. 在解决方案资源管理器中，右键单击 `UtilityLibraries` 解决方案，然后依次选择“添加”、“新建项目”。

1. 在“添加新项目”对话框中，选择 C# 节点，然后选择“.NET Standard”。 

   > [!NOTE]
   > 由于我们的库是针对 .NET Standard，而不是特定的 .NET 实现，因此可以从支持此 .NET Standard 的任何 .NET 实现对其进行调用。 有关详细信息，请参阅 [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard)。

1. 在右窗格中选择“类库(.NET Standard)”模板，然后在“名称”文本框中输入 `StringLibrary`，如下图所示：

   ![“添加新项目”对话框](./media/lut-start/add-project-cs.png)

1. 选择“确定”创建项目。

1. 将代码窗口中的所有现有代码替换为以下代码：

   [!code-csharp[StringLibrary source code](samples/csharp/utilitylibraries/stringlibrary/class1.cs)]

   `StringLibrary` 有三种静态方法：

      - 如果字符串以大写字符开头，则 `StartsWithUpper` 返回 `true`；否则返回 `false`。
      
      - 如果字符串以小写字符开头，则 `StartsWithLower` 返回 `true`；否则返回 `false`。
     
      - 如果字符串包含嵌入的空格字符，则 `HasEmbeddedSpaces` 返回 `true`；否则返回 `false`。
    
1.  从顶级的 Visual Studio 菜单中依次选择“生成”、“生成解决方案”。 Visual Studio 应会成功生成库。
 
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. 在解决方案资源管理器中，右键单击 `UtilityLibraries` 解决方案，然后依次选择“添加”、“新建项目”。

1. 在“添加新项目”对话框中，选择 Visual Basic 节点，然后选择“.NET Standard”。 

   > [!NOTE]
   > 由于我们的库是针对 .NET Standard，而不是特定的 .NET 实现，因此可以从支持此 .NET Standard 的任何 .NET 实现对其进行调用。 有关详细信息，请参阅 [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard)。

1. 在右窗格中选择“类库(.NET Standard)”模板，然后在“名称”文本框中输入 `StringLibrary`，如下图所示：

   ![“添加新项目”对话框](./media/lut-start/add-project-vb.png)

1. 选择“确定”创建项目。

1. 将代码窗口中的所有现有代码替换为以下代码：

   [!code-vb[StringLibrary source code](samples/visual-basic/utilitylibraries/stringlibrary/class1.vb)]

   `StringLibrary` 有三种静态方法：

      - 如果字符串以大写字符开头，则 `StartsWithUpper` 返回 `true`；否则返回 `false`。
      
      - 如果字符串以小写字符开头，则 `StartsWithLower` 返回 `true`；否则返回 `false`。
     
      - 如果字符串包含嵌入的空格字符，则 `HasEmbeddedSpaces` 返回 `true`；否则返回 `false`。
    
1. 右键单击“解决方案资源管理器”中的 StringLibrary 项目，然后选择“属性”。 在“应用程序”选项卡中，删除“根命名空间”文本框中的文本，如下图所示。 根命名空间由源代码中的 [Namespace 语句](https://docs.microsoft.com/dotnet/visual-basic/language-reference/statements/namespace-statement)定义。

   ![Visual Basic 项目的“项目属性”对话框](./media/lut-start/vb-properties.png)
 
1.  从顶级的 Visual Studio 菜单中依次选择“生成”、“生成解决方案”。 Visual Studio 应会成功生成库。

---

## <a name="create-the-test-project"></a>创建测试项目

下一步是创建单元测试项目，以测试 `StringLibrary` 库。 通过执行以下步骤创建单元测试：

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. 在解决方案资源管理器中，右键单击 `UtilityLibraries` 解决方案，然后依次选择“添加”、“新建项目”。

1. 在“添加新项目”对话框中，选择 C# 节点，然后选择“.NET Core”。 

   > [!NOTE]
   > 不需要使用与类库相同的语言编写单元测试。

1. 在右窗格中选择“单元测试项目(.NET Core)”模板，然后在“名称”文本框中输入 `StringLibraryTests`，如下图所示：

   ![单元测试项目的“添加新项目”对话框](./media/lut-start/add-unit-test-cs.png)

1. 选择“确定”创建项目。

   > [!NOTE]
   > 此入门教程使用 Live Unit Testing 的 MSTest 测试框架。 还可使用 xUnit 和 NUnit 测试框架。 

1. 单元测试项目无法自动访问它正在测试的类库。 可以通过添加对类库项目的引用来提供测试库访问权限。 为此，请右键单击 `StringLibraryTests` 项目，然后依次选择“添加”、“引用”。 在“引用管理器”对话框中，确保“解决方案”选项卡处于选中状态，然后选择 `StringLibrary` 项目，如下图中所示。 

   ![“引用管理器”对话框](./media/lut-start/add-reference.png)
 
1. 将模板提供的样本单元测试代码替换为以下代码：

   [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest1.cs)]

1. 通过选择工具栏上的“保存”图标来保存你的项目。 

1. 由于单元测试代码包含一些非 ASCII 字符，因此 Visual Studio 显示以下对话框来警告我们，如果以其默认的 ASCII 格式保存文件，某些字符将会丢失。 选择“以其他编码保存”按钮。 
 
   ![选择文件编码](media/lut-start/ascii-encoding.png) 

1. 在“高级保存选项”对话框的“编码”下拉列表中，选择“Unicode (UTF-8 无签名) - 代码页 65001”，如下图所示：

   ![选择 UTF-8 编码](media/lut-start/utf8-encoding.png) 

1. 从顶级的 Visual Studio 菜单中，通过“生成”、“重新生成解决方案”编译单元测试项目。

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)

1. 在解决方案资源管理器中，右键单击 `UtilityLibraries` 解决方案，然后依次选择“添加”、“新建项目”。

1. 在“添加新项目”对话框中，选择 Visual Basic 节点，然后选择“.NET Core”。 

   > [!NOTE]
   > 不需要使用与类库相同的语言编写单元测试。

1. 在右窗格中选择“单元测试项目(.NET Core)”模板，然后在“名称”文本框中输入 `StringLibraryTests`，如下图所示：

   ![单元测试的“添加新项目”对话框](./media/lut-start/add-unit-test-vb.png)

1. 选择“确定”创建项目。

   > [!NOTE]
   > 此入门教程使用 Live Unit Testing 的 MSTest 测试框架。 还可使用 xUnit 和 NUnit 测试框架。 

1. 单元测试项目无法自动访问它正在测试的类库。 可以通过添加对类库项目的引用来提供测试库访问权限。 为此，请右键单击 `StringLibraryTests` 项目，然后依次选择“添加”、“引用”。 在“引用管理器”对话框中，确保“解决方案”选项卡处于选中状态，然后选择 `StringLibrary` 项目，如下图中所示。 

   ![“引用管理器”对话框](./media/lut-start/add-reference.png)
 
1. 将模板提供的样本单元测试代码替换为以下代码：

   [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest1.vb)]

1. 通过选择工具栏上的“保存”图标来保存你的项目。 

1. 由于单元测试代码包含一些非 ASCII 字符，因此 Visual Studio 显示以下对话框来警告我们，如果以其默认的 ASCII 格式保存文件，某些字符将会丢失。 选择“以其他编码保存”按钮。 
 
   ![选择文件编码](media/lut-start/ascii-encoding.png) 

1. 在“高级保存选项”对话框的“编码”下拉列表中，选择“Unicode (UTF-8 无签名) - 代码页 65001”，如下图所示：

   ![选择 UTF-8 编码](media/lut-start/utf8-encoding.png)

1. 从顶级的 Visual Studio 菜单中，通过“生成”、“重新生成解决方案”编译单元测试项目。

---

已创建一个类库并为其编写了几个单元测试。 现在已完成使用 Live Unit Testing 所需的预备工作。

## <a name="enable-live-unit-testing"></a>启用 Live Unit Testing

到目前为止，尽管已为 `StringLibrary` 类库编写测试，但尚未执行。 启用 Live Unit Testing 后，就会自动执行这些测试。 为此，请执行以下操作：

1. 选择包含 `StringLibrary` 代码的代码窗口（可选）。 可以是 C# 项目的 class1.cs，或者 Visual Basic 项目的 Class1.vb。 （启用 Live Unit Testing 后，通过此步骤可直观检查测试结果和代码覆盖率的范围。）

1. 从顶级的 Visual Studio 菜单中依次选择“测试”、“Live Unit Testing”和“启动”。
 
1. Visual Studio 启动 Live Unit Testing，使其自动运行所有测试。 
 
完成运行测试后，“测试资源管理器”显示整体结果和各个测试的结果。 此外，代码窗口以图形方式显示测试代码覆盖率和测试结果。 如下图所示，三项测试均已成功执行。 它还显示测试中已覆盖 `StartsWithUpper` 方法中的所有代码路径，并已成功执行这些测试（用绿色复选标记“✓”指示）。 最后，显示 `StringLibrary` 中的其他方法都没有代码覆盖率（用蓝线“”指示）。 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![启动 Live Unit testing 后的测试资源管理器和代码窗口](media/lut-start/lut-results-cs.png) 

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
![启动 Live Unit testing 后的测试资源管理器和代码窗口](media/lut-start/lut-results-vb.png) 

---  

还可通过在代码窗口中选择一个特定的代码覆盖率图标来获得有关测试覆盖率和测试结果的更多详细信息。 若要查看此详细信息，请执行以下操作：

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. 单击 `StartsWithUpper` 方法中写着 `if (String.IsNullOrWhiteSpace(s))` 的行上的绿色复选标记。 如下图所示，Live Unit Testing 指示三个测试均覆盖该行的代码，并且都已成功执行。

   ![`if` 条件语句的代码覆盖率](media/lut-start/code-coverage-cs1.png) 

1. 单击 `StartsWithUpper` 方法中写着 `return Char.IsUpper(s[0])` 的行上的绿色复选标记。 如下图所示，Live Unit Testing 指示只有两个测试覆盖该行的代码，并且都已成功执行。

   ![return 语句的代码覆盖率](media/lut-start/code-coverage-cs2.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. 单击 `StartsWithUpper` 方法中写着 `If (String.IsNullOrWhiteSpace(s)) Then` 的行上的绿色复选标记。 如下图所示，Live Unit Testing 指示三个测试均覆盖该行的代码，并且都已成功执行。

   ![`if` 条件语句的代码覆盖率](media/lut-start/code-coverage-vb1.png) 

1. 单击 `StartsWithUpper` 方法中写着 `Return Char.IsUpper(s(0))` 的行上的绿色复选标记。 如下图所示，Live Unit Testing 指示只有两个测试覆盖该行的代码，并且都已成功执行。

   ![return 语句的代码覆盖率](media/lut-start/code-coverage-vb2.png)

---

Live Unit Testing 标识的主要问题是代码覆盖率不完整。 此问题将在下一部分得以解决。 

## <a name="expand-test-coverage"></a>展开测试覆盖率

此部分将把单元测试扩展到 `StartsWithLower` 方法。 执行此操作时，Live Unit Testing 将以动态方式继续测试代码。

若要将代码覆盖率扩展到 `StartsWithLower` 方法，请执行以下操作：

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. 将以下 `TestStartsWithLower` 和 `TestDoesNotStartWithLower` 添加到项目的测试源代码文件中：

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#1)]

1. 在调用 [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse`](https://docs.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) 方法之后，立即添加以下代码来修改 `DirectCallWithNullOrEmpty` 方法。

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#2)]

1. 在你修改源代码时，Live Unit Testing 将自动执行新增的和修改后的测试。 如下图“测试资源管理器”所示，所有测试（包括已添加的两个测试和已修改的测试）都已成功。

   ![展开测试覆盖率之后的测试资源管理器。](media/lut-start/test-dynamic.png) 

1. 切换到包含 `StringLibrary` 类源代码的窗口。 Live Unit Testing 现在显示代码覆盖率已扩展到 `StartsWithLower` 方法。

    ![StartsWithLower 方法的代码覆盖率](media/lut-start/lut-extended-cs.png) 

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. 将以下 `TestStartsWithLower` 和 `TestDoesNotStartWithLower` 添加到项目的测试源代码文件中：

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#1)]

1. 在调用 [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse`](https://docs.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) 方法之后，立即添加以下代码来修改 `DirectCallWithNullOrEmpty` 方法。

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#2)]

1. 在你修改源代码时，Live Unit Testing 将自动执行新增的和修改后的测试。 如下图“测试资源管理器”所示，所有测试（包括已添加的两个测试和已修改的测试）都已成功。

   ![展开测试覆盖率之后的测试资源管理器。](media/lut-start/test-dynamic.png) 

1. 切换到包含 `StringLibrary` 类源代码的窗口。 Live Unit Testing 现在显示代码覆盖率已扩展到 `StartsWithLower` 方法。

    ![StartsWithLower 的代码覆盖率](media/lut-start/lut-extended-vb.png)

---
 
在某些情况下，“测试资源管理器”中的成功测试可能会灰显。指示某个测试当前正在执行，或测试没有再次运行，因为测试自上次执行之后不会受到任何代码更改带来的影响。

到目前为止，所有测试都已成功。 在接下来的部分中，我们将讨论如何处理测试失败的问题。

## <a name="handling-a-test-failure"></a>处理测试失败的问题

此部分将介绍如何使用 Live Unit Testing 标识、故障排除并解决测试失败的问题。 需要将测试覆盖率扩展到 `HasEmbeddedSpaces` 方法来执行此操作。

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. 将以下方法添加到测试文件：

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/unittest2.cs#3)]

1. 测试执行时，Live Unit Testing 指示 `TestHasEmbeddedSpaces` 方法失败，如下图所示：![报告失败的测试的测试资源管理器。](media/lut-start/test-failure.png) 
 
1. 选择显示库代码的窗口。 请注意，Live Unit Testing 已将代码覆盖率扩展到 `HasEmbeddedSpaces` 方法。 它还报告测试失败，方法是将一个红色“🞩”添加到被失败的测试覆盖的行。 

1. 将鼠标悬停在有 `HasEmbeddedSpaces` 方法签名的行上。 Live Unit Testing 会显示一个工具提示，报告该方法被某个测试覆盖，如下图所示：

   ![失败的测试上的 Live Unit Testing 信息。](media/lut-start/test-failure-info-cs.png) 

1. 选择失败的“TestHasEmbeddedSpaces”测试。 请注意，Live Unit Testing 提供了多个选项，例如运行所有测试、运行选定测试、调试所有测试以及调试选定测试，如下图所示：

   ![失败的测试的 Live Unit Testing 选项。](media/lut-start/test-failure-options.png) 
    
1. 选择“调试选定的测试”，调试失败的测试。 
 
1. Visual Studio 在调试模式下执行测试。 测试将数组中的每个字符串分配给名为 `phrase` 的变量，并将其传递给 `HasEmbeddedSpaces` 方法。 程序执行暂停，并在断言表达式第一次为 `false` 时调用调试程序。 下图显示了 [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue`](https://docs.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) 方法调用中的意外值导致的异常对话框。  

   ![Live Unit Testing 异常对话框。](media/lut-start/exception-dialog-cs.png) 
 
   此外，Visual Studio 提供的所有调试工具均可帮助我们对失败的测试进行故障排除，如下图所示：
 
   ![Visual Studio 调试工具。](media/lut-start/debugging-tools-cs.png) 

   请注意，在“自动”窗口中，`phrase` 变量的值是“Name\tDescription”，它是数组的第二个元素。 测试方法需要 `HasEmbeddedSpaces` 在传递该字符串时返回 `true`；而它返回 `false`。 显然，这是因为它无法将制表符“\t”识别为嵌入的空格。

1. 依次选择“调试”、“继续”（按 F5 或单击工具栏上的“继续”按钮），继续执行该测试程序。 由于出现未经处理的异常，测试终止。

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. 将以下方法添加到测试文件：

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/unittest2.vb#3)]

1. 测试执行时，Live Unit Testing 指示 `TestHasEmbeddedSpaces` 方法失败，如下图所示：
 
   ![报告失败的测试的测试资源管理器。](media/lut-start/test-failure.png) 
 
1. 选择显示库代码的窗口。 请注意，Live Unit Testing 已将代码覆盖率扩展到 `HasEmbeddedSpaces` 方法。 它还报告测试失败，方法是将一个红色“🞩”添加到被失败的测试覆盖的行。 

1. 将鼠标悬停在有 `HasEmbeddedSpaces` 方法签名的行上。 Live Unit Testing 会显示一个工具提示，报告该方法被某个测试覆盖，如下图所示：

   ![失败的测试上的 Live Unit Testing 信息。](media/lut-start/test-failure-info-vb.png) 

1. 选择失败的“TestHasEmbeddedSpaces”测试。 请注意，Live Unit Testing 提供了多个选项，例如运行所有测试、运行选定测试、调试所有测试以及调试选定测试，如下图所示：

   ![失败的测试的 Live Unit Testing 选项。](media/lut-start/test-failure-options.png) 
    
1. 选择“调试选定的测试”，调试失败的测试。 
 
1. Visual Studio 在调试模式下执行测试。 测试将数组中的每个字符串分配给名为 `phrase` 的变量，并将其传递给 `HasEmbeddedSpaces` 方法。 程序执行暂停，并在断言表达式第一次为 `false` 时调用调试程序。 下图显示了 [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue`](https://docs.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) 方法调用中的意外值导致的异常对话框。  

   ![Live Unit Testing 异常对话框。](media/lut-start/exception-dialog-vb.png) 
 
   此外，Visual Studio 提供的所有调试工具均可帮助我们对失败的测试进行故障排除，如下图所示：
 
   ![Visual Studio 调试工具。](media/lut-start/debugging-tools-vb.png) 

   请注意，在“自动”窗口中，`phrase` 变量的值为“Name”+ vbTab +“Description”，它是数组的第二个元素。 测试方法需要 `HasEmbeddedSpaces` 在传递该字符串时返回 `true`；而它返回 `false`。 显然，这是因为它无法将制表符识别为嵌入的空格。

1. 依次选择“调试”、“继续”（按 F5 或单击工具栏上的“继续”按钮），继续执行该测试程序。 由于出现未经处理的异常，测试终止。

--- 

本文提供对 bug 进行初步调查的足够信息。 测试例程 `TestHasEmbeddedSpaces` 进行了错误的假设，或者 `HasEmbeddedSpaces` 无法正确识别所有嵌入的空格。 若要诊断并更正问题，请从 `StringLibrary.HasEmbeddedSpaces` 方法开始：

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. 查看 `HasEmbeddedSpaces` 方法中的比较。 它认为嵌入的空格是U + 0020。 但是，Unicode 标准包含许多其他空格字符。 这表明库代码对空格字符进行了错误的测试。
 
1. 将相等比较替换为对 <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> 方法的调用：

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/program2.cs#1)]

1. Live Unit Testing 自动重新运行失败的测试方法，并在代码窗口和“测试资源管理器”中更新结果，如下图所示：

    ![成功的 HasEmbeddedSpaces 测试。](media/lut-start/test-success-cs.png) 

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. 查看 `HasEmbeddedSpaces` 方法中的比较。 它认为嵌入的空格是U + 0020。 但是，Unicode 标准包含许多其他空格字符。 这表明库代码对空格字符进行了错误的测试。
 
1. 将相等比较替换为对 <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> 方法的调用：

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/class2.vb#1)]

1. Live Unit Testing 自动重新运行失败的测试方法，并在代码窗口和“测试资源管理器”中更新结果，如下图所示：

    ![成功的 HasEmbeddedSpaces 测试。](media/lut-start/test-success-vb.png) 

---

## <a name="see-also"></a>请参阅
[Visual Studio 中的 Live Unit Testing](live-unit-testing.md)   
[Live Unit Testing 常见问题解答](live-unit-testing-faq.md)   
