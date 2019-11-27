---
title: Класс decay
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::decay
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
ms.openlocfilehash: 3b22dfecb1162ce67a0d648197465115acb044ba
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688117"
---
# <a name="decay-class"></a>Класс decay

Создает тип, как передано по значению. Создает тип, не являющийся ссылочным, константным, временным, или создает указатель на тип из функции или типа массива.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct decay;

template <class T>
using decay_t = typename decay<T>::type;
```

### <a name="parameters"></a>Параметры

*T* \
Тип для изменения.

## <a name="remarks"></a>Заметки

Используйте шаблон decay для создания результирующего типа, как если бы тип был передан по значению в качестве аргумента. Typedef члена шаблона класса `type` содержит измененный тип, который определен на следующих этапах:

- Тип `U` определяется как `remove_reference<T>::type`.

- Если `is_array<U>::value` имеет значение true, измененный тип `type` имеет значение `remove_extent<U>::type *`.

- Если же `is_function<U>::value` имеет значение true, измененный тип `type` имеет значение `add_pointer<U>::type`.

- В противном случае измененный тип `type` имеет значение `remove_cv<U>::type`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
