---
title: Классы коллекций ATL и перечислителей
ms.date: 11/04/2016
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
ms.openlocfilehash: a0d7483cc142377ec4de903e27f23056a9e8dd8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495311"
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
|[_Копировать](../atl/atl-copy-policy-classes.md)|Класс политики копирования|
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Класс политики копирования|
|[CAdapt](../atl/reference/cadapt-class.md)|Класс адаптера (скрывает **оператор &** позволяя `CComPtr`, `CComQIPtr`, и `CComBSTR` для сохранения в контейнеры стандартной библиотеки C++)|

## <a name="see-also"></a>См. также

[Коллекции и перечислители](../atl/atl-collections-and-enumerators.md)

