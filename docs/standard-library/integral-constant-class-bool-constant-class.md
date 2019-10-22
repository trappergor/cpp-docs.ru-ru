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
ms.openlocfilehash: 9577ce51d4b0773f7b309fe3dc6dcb5820693dcb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689534"
---
# <a name="integral_constant-class-bool_constant-class"></a>Класс integral_constant, класс bool_constant

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

*T* \
Тип константы.

*v* \
Значение константы.

## <a name="remarks"></a>Заметки

Шаблон класса `integral_constant`, если он специализирован с целочисленным типом *t* и значением *v* этого типа, представляет объект, содержащий константу этого целочисленного типа с указанным значением. Член с именем `type` является псевдонимом для типа специализации созданного шаблона и член `value` хранит значение *v*, которое используется для создания специализации.

Шаблон класса `bool_constant` является явной частичной специализацией `integral_constant`, в которой в качестве аргумента *t* используется **bool** .

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

[<type_traits>](../standard-library/type-traits.md)\
[false_type](../standard-library/type-traits-typedefs.md#false_type) \
[true_type](../standard-library/type-traits-typedefs.md#true_type)
