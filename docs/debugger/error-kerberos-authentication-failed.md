---
title: "错误： Kerberos 身份验证失败 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.callback_kerberos_auth_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: c18053f9-9074-4bc3-a8bf-13e4acbea921
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37dc0626a1f96d20aa7cf1cb4a3ca2d811d391b4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="error-kerberos-authentication-failed"></a>错误：Kerberos 身份验证失败
当尝试进行远程调试时，可能会收到以下错误消息：  
  
```  
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Kerberos authentication failed.  
```  
  
 当 Visual Studio 远程调试器监视器在“本地系统”帐户或“网络服务”帐户下运行时，会发生此错误。 在其中任何一个帐户下，远程调试器都必须建立 Kerberos 身份验证连接，以便向 Visual Studio 调试器主机提供反馈。  
  
 Kerberos 身份验证在下列条件下不可用：  
  
-   目标计算机或调试器主机位于工作组中，而不是位于域中  
  
     \- 或 -  
  
-   域控制器上已禁用 Kerberos。  
  
 如果 Kerberos 身份验证不可用，请更改用于运行 Visual Studio 远程调试监视器的帐户。 有关过程，请参阅[错误： 目标计算机上的 Visual Studio 远程调试器服务无法重新连接到此计算机](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md)。  
  
 如果这两台计算机都连接到同一域，而您仍然收到此消息，请验证目标计算机上的 DNS 是否正确解析了调试器主机的名称。 请参见下面的步骤。  
  
### <a name="to-verify-that-dns-on-the-target-computer-is-correctly-resolving-the-debugger-host-computer-name"></a>验证目标计算机上的 DNS 是否正确解析了调试器主机名称  
  
1.  在目标计算机上打开**启动**菜单上，指向**附件**，然后单击**命令提示符**。  
  
2.  在**命令提示符**窗口中，键入：  
  
    ```  
    ping <debugger_host_computer_name>  
    ```  
  
3.  `ping` 响应的第一行显示了 DNS 为指定计算机返回的完整计算机名称和 IP 地址。  
  
4.  调试器主机计算机上，打开**命令提示符**窗口并运行`ipconfig`。  
  
5.  比较 IP 地址值。  
  
## <a name="see-also"></a>另请参阅  
 [远程调试错误和疑难解答](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [远程调试](../debugger/remote-debugging.md)