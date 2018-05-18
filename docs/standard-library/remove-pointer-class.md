---
title: Класс remove_pointer | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_pointer
dev_langs:
- C++
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 745711e1dd5abde022d0a21d5cb1ea6c013931a8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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

`T` Тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `remove_pointer<T>` содержит измененный тип, т.е. `T1`, если `T` имеет форму `T1*`, `T1* const`, `T1* volatile` или `T1* const volatile`; в противном случае — `T`.

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

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс add_pointer](../standard-library/add-pointer-class.md)<br/>
