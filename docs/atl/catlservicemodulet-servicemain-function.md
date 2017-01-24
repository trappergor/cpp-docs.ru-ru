---
title: "CAtlServiceModuleT::ServiceMain Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceMain"
  - "CServiceModule::ServiceMain"
  - "CServiceModule.ServiceMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ServiceMain method"
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::ServiceMain Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Диспетчеру служб вызывает `ServiceMain` при открытии приложение панель управления службы, выберите служба и нажмите кнопку **Пуск**.  
  
 После того, как диспетчер служб вызывает `ServiceMain` служба должна предоставить диспетчер служб функцию обработчика.  Эта функция позволяет диспетчеру служб получить состояние службы и передать определенных инструкций \(такие как приостанавливать или останавливать\).  Диспетчер служб возвращает эту функцию, когда служба передает **\_Handler** к функции api\-интерфейса Win32, [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054).  \(**\_Handler** функция статического члена, которая вызывает функцию\-член [обработчик](../Topic/CAtlServiceModuleT::Handler%20Function.md)\), не являющихся статическими.  
  
 При запуске служба должна также информировать диспетчер служб его текущего состояния.  Это делается путем передачи **SERVICE\_START\_PENDING** к функции api\-интерфейса Win32, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain` затем вызывает `CAtlExeModuleT::InitializeCom`, который вызывает функцию Win32 API [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279).  По умолчанию `InitializeCom` передает пометить **COINIT\_MULTITHREADED** функции.  Этот пометить указывает, что программа продетым быть свободен\- потоков сервером.  
  
 Теперь, вызываются `CAtlServiceModuleT::Run` выполнения главный работы службы.  **Запуск** продолжает выполняться до тех пор, пока служба не остановлена.  
  
## См. также  
 [Службы](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)