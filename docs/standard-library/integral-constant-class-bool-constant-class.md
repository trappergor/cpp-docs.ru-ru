---
title: Класс integral_constant, класс bool_constant
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
helpviewer_keywords:
- std::integral_constant [C++]
- std::bool_constant [C++]
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
ms.openlocfilehash: f7b9217560bc94c536a7c819276266fd16fa4b07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404875"
---
# <a name="integralconstant-class-boolconstant-class"></a>Класс integral_constant, класс bool_constant

Создает целочисленную константу из типа и значения.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T, T v>
struct integral_constant {
   static constexpr T value = v;
   typedef T value_type;
   typedef integral_constant<T, v> type;
   constexpr operator value_type() const noexcept;
   constexpr value_type operator()() const noexcept;
   };
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип константы.

*v*<br/>
Значение константы.

## <a name="remarks"></a>Примечания

Класс шаблона `integral_constant`, если он специализирован с целочисленным типом *T* и значением *v* этого типа, представляет объект, который содержит константу этого целочисленного типа с указанным значением. Член с именем `type` является псевдонимом для типа специализации созданного шаблона и член `value` хранит значение *v*, которое используется для создания специализации.

`bool_constant` Класс-шаблон — это явная частичная специализация `integral_constant` , использующий **bool** как *T* аргумент.

## <a name="example"></a>Пример

```cpp
// std__type_traits__integral_constant.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "integral_constant<int, 5> == "
        << std::integral_constant<int, 5>::value << std::endl;
    std::cout << "integral_constant<bool, false> == " << std::boolalpha
        << std::integral_constant<bool, false>::value << std::endl;

    return (0);
    }
```

```Output
integral_constant<int, 5> == 5
integral_constant<bool, false> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[false_type](../standard-library/type-traits-typedefs.md#false_type)<br/>
[true_type](../standard-library/type-traits-typedefs.md#true_type)<br/>
