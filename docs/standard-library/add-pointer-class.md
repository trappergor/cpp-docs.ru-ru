---
title: Класс add_pointer
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_pointer
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
ms.openlocfilehash: 8adeffd0352d04fe844b286ea7456c66e907a0a7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619265"
---
# <a name="add_pointer-class"></a>Класс add_pointer

Создает указатель на тип из указанного типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Параметры

*T*\
Тип для изменения.

## <a name="remarks"></a>Комментарии

Typedef элемента **typedef** `type` именуется тем же типом, что и `remove_reference<T>::type*` . Псевдоним `add_pointer_t` является ярлыком для доступа к определению **типа** члена `type` .

Поскольку его нельзя использовать для создания указателя из ссылки, `add_pointer` удаляет ссылку (если таковая имеется) из указанного типа, прежде чем создать указатель на тип. Следовательно, можно использовать тип с `add_pointer` вне зависимости от того, является ли данный тип ссылкой.

## <a name="example"></a>Пример

В следующем примере показано, что `add_pointer` типа аналогичен указателю на данный тип.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[<type_traits>](type-traits.md)\
[Класс remove_pointer](remove-pointer-class.md)
