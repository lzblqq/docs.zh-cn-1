---
title: "如何：在可靠会话内交换消息 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 如何：在可靠会话内交换消息
本主题概述了使用系统提供的绑定之一来启用可靠会话所需的步骤。这些绑定支持可靠会话，但默认情况下不支持。可使用代码以强制方式或在配置文件中以声明方式以启用可靠会话。此过程使用客户端和服务配置文件来启用可靠会话，并规定消息按照发送的相同顺序到达。  
  
 此过程的关键部分是终结点配置元素包含一个 `bindingConfiguration` 属性，该属性引用一个名为“Binding1”的绑定配置。[\<绑定\>](../../../../docs/framework/misc/binding.md) 配置元素然后可以引用此名称，通过将 [reliableSession](http://msdn.microsoft.com/zh-cn/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) 元素的 `enabled` 属性设置为 `true` 来启用可靠会话。通过将 `ordered` 属性设置为 `true`，可为可靠会话指定有序传送保证。  
  
 有关此示例的源副本，请参见 [WS 可靠会话](../../../../docs/framework/wcf/samples/ws-reliable-session.md)。  
  
### 使用 WSHttpBinding 配置服务以使用可靠会话  
  
1.  为该类型的服务定义服务协定。  
  
     [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]  
  
2.  在服务类中实现该服务协定。请注意，在服务的实现内部，未指定地址或绑定信息。而且，不必编写代码也可从配置文件中检索该信息。  
  
     [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]  
  
3.  创建 Web.config 文件以配置 `CalculatorService` 的终结点，该终结点将 <xref:System.ServiceModel.WSHttpBinding> 与启用的可靠会话和所需的消息有序传送一起使用。  
  
     [!code[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]  
  
4.  创建包含以下代码行的 Service.svc 文件：  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  将 Service.svc 文件放到 Internet 信息服务 \(IIS\) 虚拟目录中。  
  
### 使用 WSHttpBinding 配置客户端以使用可靠会话  
  
1.  从命令行使用 [ServiceModel 元数据实用工具 \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 以从服务元数据生成代码：  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  生成的客户端包含 `ICalculator` 接口，该接口定义了客户端实现必须满足的服务协定。  
  
     [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]  
  
3.  生成的客户端应用程序还包含 `ClientCalculator` 的实现。请注意，在服务的实现内部，未指定地址和绑定信息。而且，不必编写代码也可从配置文件中检索该信息。  
  
     [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]  
  
4.  Svcutil.exe 还为使用 <xref:System.ServiceModel.WSHttpBinding> 类的客户端生成配置。在使用 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 时，应在 App.config 文件中命名此文件。  
  
     [!code[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]  
  
5.  在应用程序中创建 `ClientCalculator` 的实例，然后调用服务操作。  
  
     [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]  
  
6.  编译并运行客户端。  
  
## 示例  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 默认情况下，有多种系统提供的绑定支持可靠会话。这些绑定包括：  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>  
  
 有关如何创建支持可靠会话的自定义绑定的示例，请参见[如何：创建使用 HTTPS 的自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)。  
  
## 请参阅  
 [可靠会话](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)