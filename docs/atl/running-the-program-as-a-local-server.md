---
title: "Running the Program as a Local Server | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL services, running as local servers"
  - "отладка [ATL], running services as local server"
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Running the Program as a Local Server
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если запустить программу в качестве службы неудобн, можно временно изменить реестр, чтобы программа будет выполнитьа как обычный локальный сервер.  Просто переименуйте значение `LocalService`, произведенных в `_LocalService` под AppID и убедитесь, что ключ `LocalServer32` под вашим CLSID установлен правильно.  \(Следует отметить, с помощью DCOMCNFG для указания, что приложение должно быть выполнитьо на другом компьютере переименовывает `_LocalServer32``LocalServer32` к пользовательским ключом\). Запустить программу, как локальный сервер принимает несколько более секунд при запуске, поскольку вызов **StartServiceCtrlDispatcher** в `CAtlServiceModuleT::Start` занимает несколько секунд, прежде чем он завершается ошибкой.  
  
## См. также  
 [Debugging Tips](../atl/debugging-tips.md)