---
title: "关于异常的疑难解答：System.ServiceModel.Security.MessageSecurityException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.ServiceModel.Security.MessageSecurityException 异常"
  - "MessageSecurityException 异常"
ms.assetid: 61ad69a1-ac50-49de-9a7c-8454a84ec5bd
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 关于异常的疑难解答：System.ServiceModel.Security.MessageSecurityException
当 <xref:System.ServiceModel.Security.MessageSecurityException> 确定消息未受到正确保护或已被篡改时，将引发 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 异常。 当下列条件全为真时，此错误会非常频繁地发生：  
  
-   在远程连接（如远程桌面连接或终端服务）上使用 WCF 服务引用与网站或 Web 应用程序项目中的 WCF 服务 \(.svc\) 进行通信。  
  
-   您不具有远程站点上的管理员权限。  
  
-   对远程站点上的本地主机的请求由 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server 进行处理。  
  
## 相关提示  
 **使用 ASP.Net 开发服务器时解决 NTLM 身份验证问题。**  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server 通常会关闭允许匿名访问的 Windows NT 质询\/响应 \(NTLM\) 安全。 默认情况下，当您运行终端服务会话或使用远程连接时，将启用 NTLM 安全。 启用 NTLM 时，将根据启动 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server 的用户或进程的凭据验证所有本地主机请求。 这样可减少安全威胁。 但是，WCF 还会执行自己的身份验证，并且不允许非管理员帐户使用 WCF 服务。  
  
 如果远程用户可能通过使用 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server 来运行网站，并且还使用 Web 服务或 WCF 服务，则可以创建自定义服务绑定或关闭 NTLM 安全。  
  
> [!IMPORTANT]
>  建议不要关闭 NTLM 安全功能，否则可能构成安全威胁。  
  
 如果创建自定义服务绑定，仍然可以受 NTLM 身份验证保护。  
  
 使用以下步骤为 WCF 服务创建自定义服务绑定。  
  
#### 为 ASP.NET 开发服务器中承载的 WCF 服务创建自定义服务绑定  
  
1.  打开生成异常的 WCF 服务的 Web.config 文件。  
  
2.  在该 Web.config 文件中输入以下信息。  
  
    ```  
    <bindings> <customBinding> <binding name="Service1Binding"> <transactionFlow /> <textMessageEncoding /> <httpTransport authenticationScheme="Ntlm" /> </binding> </customBinding> </bindings>  
    ```  
  
3.  保存并关闭 Web.config 文件。  
  
4.  在 WCF 或 Web 服务的代码中，将终结点值更改为下面的值：  
  
    ```  
    <endpoint address="" binding="customBinding" bindingConfiguration="Service1Binding" contract="IService1" />  
    ```  
  
     这样可确保服务使用自定义绑定。  
  
5.  在访问服务的 Web 应用程序中，添加对服务的引用。 （在**“添加服务引用”**对话框中，添加对服务的引用，就像处理生成异常的原始服务一样。）  
  
 在处理 WCF 服务引用时，可以按照以下步骤来禁用 NTLM 安全。  
  
> [!IMPORTANT]
>  建议不要关闭 NTLM 安全功能，否则可能构成安全威胁。  
  
#### 关闭 NTLM 安全  
  
1.  在**“解决方案资源管理器”**中，右击网站名称，然后单击**“属性页”**。  
  
2.  选择**“启动选项”**，然后清除**“NTLM 身份验证”**复选框。  
  
3.  单击“确定”。  
  
## 请参阅  
 <xref:System.ServiceModel.Security.MessageSecurityException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)