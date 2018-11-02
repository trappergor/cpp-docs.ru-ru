---
title: operator!=
ms.date: 11/04/2016
f1_keywords:
- std::!=
- '!='
- std::operator!=
- std.operator!=
- std.!=
- operator!=
helpviewer_keywords:
- '!= operator'
- operator!=
- operator !=
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
ms.openlocfilehash: a3a750565f16a0a01770cea16bf91918887095f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574252"
---
# <a name="operator"></a>operator!=

> [!NOTE]
> Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегружает `operator!=` для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator!=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает `!(left == right)`.

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)<br/>
