---
title: Коллекция ATL и классы перечислитель | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a47525bb21b896b0fef8393cab66142ed40311ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354450"
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

