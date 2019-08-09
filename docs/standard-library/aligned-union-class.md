---
title: Класс aligned_union
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::aligned_union
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
ms.openlocfilehash: b9ffb4aff4d4d5667ab8d626ea13a21da94ca0c1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456466"
---
# <a name="alignedunion-class"></a>Класс aligned_union

Предоставляет достаточно большой и должным образом выровненный тип POD для хранения типа объединения и требуемого размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Len, class... Types>
struct aligned_union;

template <std::size_t Len, class... Types>
using aligned_union_t = typename aligned_union<Len, Types...>::type;
```

### <a name="parameters"></a>Параметры

*Len*\
Значение выравнивания для самого крупного типа в объединении.

*Типы*\
Различные типы в базовом объединении.

## <a name="remarks"></a>Примечания

Используйте этот класс шаблона для получения выравнивания и размера, необходимого для хранения объединения в неинициализированном хранилище. Typedef `type` элемента именует тип POD, подходящий для хранения любого типа, указанного в списке *типы*; минимальный размер — *Len*. Статический член `alignment_value` типа `std::size_t` содержит строгое выравнивание, необходимое для всех типов, перечисленных в списке *типы*.

## <a name="example"></a>Пример

В следующем примере показано, как использовать `aligned_union` для выделения буфера выровненного стека для размещения объединения.

```cpp
// std__type_traits__aligned_union.cpp
#include <iostream>
#include <type_traits>

union U_type
{
    int i;
    float f;
    double d;
    U_type(float e) : f(e) {}
};

typedef std::aligned_union<16, int, float, double>::type aligned_U_type;

int main()
{
    // allocate memory for a U_type aligned on a 16-byte boundary
    aligned_U_type au;
    // do placement new in the aligned memory on the stack
    U_type* u = new (&au) U_type(1.0f);
    if (nullptr != u)
    {
        std::cout << "value of u->i is " << u->i << std::endl;
        // must clean up placement objects manually!
        u->~U_type();
    }
}
```

```Output
value of u->i is 1065353216
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Класс alignment_of](../standard-library/alignment-of-class.md)
