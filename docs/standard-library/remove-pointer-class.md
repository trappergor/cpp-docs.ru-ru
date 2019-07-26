---
title: Класс remove_pointer
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_pointer
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
ms.openlocfilehash: 786a1cba5fc35014e33e3e19245271adefec1372
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451252"
---
# <a name="removepointer-class"></a>Класс remove_pointer

Делает тип из указателя на тип.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct remove_pointer;

template <class T>
using remove_pointer_t = typename remove_pointer<T>::type;
```

### <a name="parameters"></a>Параметры

*T*\
Тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `remove_pointer<T>` содержит модифицированный тип, который имеет `T1` значение, если *t* `T1*`имеет форму, `T1* volatile` `T1* const`, или `T1* const volatile`, в противном случае *t*.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_pointer_t<int *> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_pointer_t<int *> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_pointer_t<int *> == int
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Класс add_pointer](../standard-library/add-pointer-class.md)
