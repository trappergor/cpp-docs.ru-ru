---
title: Класс контейнера::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: 2c2b87e8cc51248fd3d29df7f361fff92da72957
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494501"
---
# <a name="container-classswap"></a>Класс контейнера::swap

> [!NOTE]
> Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Меняет местами управляемые последовательности между **\*this**.

## <a name="syntax"></a>Синтаксис

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Примечания

Если **\*this.get\_allocator ==** _right_**.get_allocator**, перестановка выполняется в постоянном времени. В противном случае она выполняет ряд назначений элементов и вызовов конструктора, пропорционально количеству элементов в двух управляемых последовательностях.

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)<br/>
