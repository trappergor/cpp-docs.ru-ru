---
title: "ATL Collection and Enumerator Classes | Microsoft Docs"
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
  - "классы коллекций, ATL - библиотека"
  - "перечислители, ATL - классы"
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Collection and Enumerator Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотеки ATL предоставляет следующие классы, позволяющие реализовать и перечислителям коллекций.  
  
|Класс|Описание|  
|-----------|--------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Реализация интерфейса коллекции|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Реализация интерфейса перечислителя \(принимает данные, хранящиеся в контейнере STL\- совместимого\)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Реализация интерфейса перечислителя \(принимает данные, хранящиеся в массиве\)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Реализация интерфейса объекта перечислителя \(использования `IEnumOnSTLImpl`\)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|Реализация интерфейса объекта перечислителя \(использования `CComEnumImpl`\)|  
|[\_Copy](../Topic/ATL%20Copy%20Policy%20Classes.md)|Класс политики копирования|  
|[\_CopyInterface](../Topic/ATL%20Copy%20Policy%20Classes.md)|Класс политики копирования|  
|[CAdapt](../atl/reference/cadapt-class.md)|Класс адаптера \(hide **operator &** позволяя `CComPtr`, `CComQIPtr` и `CComBSTR`, сохраняемый в контейнерах STL\)|  
  
## См. также  
 [Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)