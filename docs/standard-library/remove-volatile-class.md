---
title: Класс remove_volatile | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_volatile
dev_langs:
- C++
helpviewer_keywords:
- remove_volatile class
- remove_volatile
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1cd2b4882c4b5e62a2f6574b3011b74747e412b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858504"
---
# <a name="removevolatile-class"></a>Класс remove_volatile

Создает долговременный тип из типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct remove_volatile;

template <class T>
using remove_volatile_t = typename remove_volatile<T>::type;
```

### <a name="parameters"></a>Параметры

`T` Тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `remove_volatile<T>` содержит измененный тип, т. е. `T1`, если `T` имеет форму `volatile T1`; в противном случае — `T`.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_volatile_t<volatile int> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << " remove_volatile_t<volatile int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_volatile_t<volatile int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс add_volatile](../standard-library/add-volatile-class.md)<br/>
