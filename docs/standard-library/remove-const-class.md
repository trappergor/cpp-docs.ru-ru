---
title: Класс remove_const
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::remove_const
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
ms.openlocfilehash: 04f7c6475d88f843ef381563f80559529e6b59e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477185"
---
# <a name="removeconst-class"></a>Класс remove_const

Создает неконстантный тип из типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct remove_const;
```

```cpp
template <class T>
using remove_const_t = typename remove_const<T>::type;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `remove_const<T>` содержит модифицированный тип, который является `T1` при *T* имеет форму `const T1`, в противном случае *T*.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_const_t<const int>*)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_const_t<const int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_const_t<const int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс add_const](../standard-library/add-const-class.md)<br/>
[Класс remove_cv](../standard-library/remove-cv-class.md)<br/>
