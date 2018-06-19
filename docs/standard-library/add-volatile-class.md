---
title: Класс add_volatile | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf15ef0b5134af7831cf2e71b4235df9534f3425
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841301"
---
# <a name="addvolatile-class"></a>Класс add_volatile

Создает тип volatile из указанного типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Параметры

*T* тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр `add_volatile<T>` содержит определение типа члена `type`, который является *T*, если *T* является ссылкой, функцией или типом с квалификатором volatile; в противном случае — `volatile` *T*. Псевдоним `add_volatile_t` является ярлыком для доступа к определению типа `type`.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс remove_volatile](../standard-library/remove-volatile-class.md)<br/>
