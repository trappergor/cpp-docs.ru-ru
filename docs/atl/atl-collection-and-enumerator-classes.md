---
title: Классы коллекций ATL и перечислителей | Документация Майкрософт
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
ms.openlocfilehash: c0ff5fec4749e08826bab5572149c6cd24a204f9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765077"
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

