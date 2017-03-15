---
title: "CAtlServiceModuleT::Start Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule.Start"
  - "CServiceModule::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start - метод"
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::Start Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Запустить, когда служба **\_tWinMain** вызывает  **CAtlServiceModuleT::WinMain**, которая, в свою очередь, вызывает `CAtlServiceModuleT::Start`.  
  
 `CAtlServiceModuleT::Start` настраивает массив структур **SERVICE\_TABLE\_ENTRY**, сопоставить каждая служба в его запуске функции.  Затем этот массив передается в функцию Win32 API, [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324).  Теоретически одно EXE может обрабатывать несколько служб и массив может иметь несколько структур **SERVICE\_TABLE\_ENTRY**.  В настоящее время, однако, сервисные поддержки Библиотека ATL\-, сформированные только одна служба в EXE\-ФАЙЛА.  Поэтому массив имеет один ввод, содержащий имя службы и **\_ServiceMain** запускаемым функция.  Функция **\_ServiceMain** статического элемента `CAtlServiceModuleT`, которая вызывает функцию\-член, не являющихся статическими, `ServiceMain`.  
  
> [!NOTE]
>  Сбой **StartServiceCtrlDispatcher** подключиться к диспетчеру служб \(диспетчер служб\), вероятно, значит, что программа не запускается как служба.  В этом случае программа вызывает `CAtlServiceModuleT::Run` непосредственно так, чтобы программа могла выполняться как локальный сервер.  Дополнительные сведения о запуске программы в качестве локального сервера см. в разделе [Советы по отладке](../atl/debugging-tips.md).  
  
## См. также  
 [Службы](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)