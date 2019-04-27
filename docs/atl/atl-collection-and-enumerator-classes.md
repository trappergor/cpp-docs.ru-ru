---
title: Классы коллекций ATL и перечислителей
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: b1ab9a160b01ea278d162a515e5121054bf398f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252329"
---
# <a name="atl-collection-and-enumerator-classes"></a>Классы коллекций ATL и перечислителей

Библиотека ATL предоставляет следующие классы для реализации коллекции и перечислители.

|Класс|Описание|
|-----------|-----------------|
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Реализация интерфейса коллекции|
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Реализация интерфейса перечислителя (предполагается, что данные, хранящиеся в контейнере совместимые библиотеки C++ Standard)|
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Реализация интерфейса перечислителя (предполагается, что данные, хранящиеся в массив)|
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Реализация объекта перечислителя (использует `IEnumOnSTLImpl`)|
|[CComEnum](../atl/reference/ccomenum-class.md)|Реализация объекта перечислителя (использует `CComEnumImpl`)|
|[_Copy](../atl/atl-copy-policy-classes.md)|Класс политики копирования|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Класс политики копирования|
|[CAdapt](../atl/reference/cadapt-class.md)|Класс адаптера (скрывает **оператор &** позволяя `CComPtr`, `CComQIPtr`, и `CComBSTR` для сохранения в контейнеры стандартной библиотеки C++)|

## <a name="see-also"></a>См. также

[Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)
