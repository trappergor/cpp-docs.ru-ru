---
title: Класс add_pointer | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c5f352f684818009210b4d394f4a820159da053
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101954"
---
# <a name="addpointer-class"></a>Класс add_pointer

Создает указатель на тип из указанного типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип для изменения.

## <a name="remarks"></a>Примечания

Элемент **typedef** `type` именует тот же тип как `remove_reference<T>::type*`. Псевдоним `add_pointer_t` является ярлыком для доступа к члену **typedef** `type`.

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

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс remove_pointer](../standard-library/remove-pointer-class.md)<br/>
