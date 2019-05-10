---
title: Класс контейнера::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: b344747c42e9b8b751b97747aacec0b39d10d6a1
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221526"
---
# <a name="container-classswap"></a>Класс контейнера::swap

> [!NOTE]
> Этот раздел находится в Microsoft C++ документации в качестве нефункционального примера контейнеров, используемых в C++ стандартной библиотеки. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Меняет местами управляемые последовательности между **\*this**.

## <a name="syntax"></a>Синтаксис

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Примечания

Если **\*this.get\_allocator ==** _right_**.get_allocator**, перестановка выполняется в постоянном времени. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)<br/>
