---
title: "CAtlServiceModuleT::Run Function | Microsoft Docs"
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
  - "CServiceModule::Run"
  - "CServiceModule.Run"
  - "CSecurityDescriptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL services, безопасность"
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Run Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Запуск** содержит вызовы `PreMessageLoop`, `RunMessageLoop` и `PostMessageLoop`.  После вызова, `PreMessageLoop` сначала сохраняет идентификатор потока, службы  Служба может использовать этот идентификатор для того, чтобы закрыть, отправляя сообщение **WM\_QUIT** с помощью функции api\-интерфейса Win32, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` затем вызывает `InitializeSecurity`.  По умолчанию `InitializeSecurity` вызывает [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) со значением дескриптора безопасности null, означающее, что любой пользователь имеет доступ к объекту.  
  
 Если не нужно, чтобы определить собственную службу безопасность, то переопределение `PreMessageLoop` и не вызывает `InitializeSecurity` и модели COM затем определяет параметры безопасности из реестра.  Удобный способ настройки параметров реестра, программа [DCOMCNFG](../Topic/DCOMCNFG.md) обсуженная далее в этом разделе.  
  
 Как только безопасность указана, объект регистрации в модели COM, чтобы новые клиенты могут подключаться к программе.  Наконец, программа сообщает диспетчеру служб что она работает и программа входит в цикл обработки сообщений.  Программа остается выполнение до тех пор, пока она не будет создать прекращенное сообщение при завершении работы службы.  
  
## См. также  
 [Службы](../atl/atl-services.md)   
 [CSecurityDesc Class](../atl/reference/csecuritydesc-class.md)   
 [CSid Class](../atl/reference/csid-class.md)   
 [CDacl Class](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)