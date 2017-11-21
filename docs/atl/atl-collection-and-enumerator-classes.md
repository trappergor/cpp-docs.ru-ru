---
title: "Коллекция ATL и классы перечислитель | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5fe6a018668f40c632e0ff980499afb7e60de8ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="atl-collection-and-enumerator-classes"></a>Коллекция ATL и классы перечислителя
Библиотека ATL предоставляет следующие классы для реализации коллекции и перечислители.  
  
|Класс|Описание|  
|-----------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Реализация интерфейса коллекции|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Реализация интерфейса перечислителя (предполагается, данные, хранящиеся в контейнере совместимое библиотеки C++ Standard)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Реализация интерфейса перечислителя (предполагается данных, хранящихся в массиве)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Реализация объекта перечислителя (использует `IEnumOnSTLImpl`)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|Реализация объекта перечислителя (использует `CComEnumImpl`)|  
|[_Copy](../atl/atl-copy-policy-classes.md)|Класс политики копирования|  
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Класс политики копирования|  
|[CAdapt](../atl/reference/cadapt-class.md)|Класс адаптера (скрывает **оператор &** разрешение `CComPtr`, `CComQIPtr`, и `CComBSTR` для сохранения в контейнеры стандартной библиотеки C++)|  
  
## <a name="see-also"></a>См. также  
 [Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)

