---
title: Класс контейнера::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: ccf4ae6ebc3ca13a42ca950310a60e30dbb27034
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450774"
---
# <a name="container-classswap"></a>Класс контейнера::swap

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Меняет местами управляемые последовательности между **\*this**.

## <a name="syntax"></a>Синтаксис

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Примечания

Если **\*this.get\_allocator ==** _right_ **.get_allocator**, перестановка выполняется в постоянном времени. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)
