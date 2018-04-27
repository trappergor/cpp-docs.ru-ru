---
title: Класс add_pointer | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 102984fc0384499f5aa2538a0f8d858578096551
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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

*T* тип для изменения.

## <a name="remarks"></a>Примечания

Определение типов `type`члена именует тот же тип как `remove_reference<T>::type*`. Псевдоним `add_pointer_t` является ярлыком для доступа к определению типа `type`.

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
