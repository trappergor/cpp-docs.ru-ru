---
title: "Threading Models and Critical Sections Classes | Microsoft Docs"
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
  - "vc.atl.threads.models"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, critical sections"
  - "ATL - библиотека, многопоточность"
  - "critical sections"
  - "работа с потоками [ATL], модели"
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Threading Models and Critical Sections Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Следующие классы определяют потоковую модель и критическую секцию.  
  
-   [Класса CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) реализует поток\- пул, сервер модели COM модели изоляции.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) предоставляет методы для реализации поток\- пул, сервер модели COM модели изоляции.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) поддерживает потокобезопасные методы для увеличения и уменьшения переменную.  Предоставляет критическую секцию.  
  
-   [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md) поддерживает потокобезопасные методы для увеличения и уменьшения переменную.  Не предоставляет критическую секцию.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) предоставляет методы для увеличения и уменьшения переменную.  Не предоставляет критическую секцию.  
  
-   [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) определяет соответствующий класс потоковой модели для одного класса объектов.  
  
-   [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md) определяет соответствующий класс потоковой модели для объекта, который глобально доступен.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) содержит методы для получения и освобождение критическую секцию.  Критической секции автоматически инициализирована.  
  
-   [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) содержит методы для получения и освобождение критическую секцию.  Критическая секция должна быть явно инициализирован.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) используются методы в `CComCriticalSection` без предоставления критическую секцию.  Методы в `CComFakeCriticalSection` не выполняют никаких действий.  
  
-   [CRTThreadTraits](../Topic/CRTThreadTraits%20Class.md) предоставляет функцию создания потока CRT.  Используйте этот класс, если поток будет использовать функции CRT.  
  
-   [Win32ThreadTraits](../Topic/Win32ThreadTraits%20Class.md) предоставляет функцию создания потока Windows.  Используйте этот класс, если поток не будет использовать функции CRT.  
  
## См. также  
 [Class Overview](../atl/atl-class-overview.md)