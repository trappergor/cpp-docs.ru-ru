---
title: Класс remove_cv | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_cv
dev_langs:
- C++
helpviewer_keywords:
- remove_cv class
- remove_cv
ms.assetid: 8502602a-1c80-479c-84e0-33bd1d6496d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b14733ea906fa47e7339c23efb8942763e928828
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956313"
---
# <a name="removecv-class"></a>Класс remove_cv

Создает неконстантный/долговременный тип из типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct remove_cv;

template <class T>
using remove_cv_t = typename remove_cv<T>::type;
```

### <a name="parameters"></a>Параметры

*T* введите для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `remove_cv<T>` содержит модифицированный тип, который является `T1` при *T* имеет форму `const T1`, `volatile T1`, или `const volatile T1`, в противном случае *T*.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_cv_t<const volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_cv_t<const volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_cv_t<const volatile int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс remove_const](../standard-library/remove-const-class.md)<br/>
[Класс remove_volatile](../standard-library/remove-volatile-class.md)<br/>
