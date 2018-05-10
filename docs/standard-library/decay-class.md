---
title: Класс decay | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0451b8565a4d021181d79d15437637e1b2f3b27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
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

`T` Тип для изменения.

## <a name="remarks"></a>Примечания

Используйте шаблон decay для создания результирующего типа, как если бы тип был передан по значению в качестве аргумента. Член класса шаблона typedef `type` содержит измененный тип, который определяется на следующих этапах:

- Тип `U` определяется как `remove_reference<T>::type`.

- Если `is_array<U>::value` имеет значение true, измененный тип `type` имеет значение `remove_extent<U>::type *`.

- Если же `is_function<U>::value` имеет значение true, измененный тип `type` имеет значение `add_pointer<U>::type`.

- В противном случае измененный тип `type` имеет значение `remove_cv<U>::type`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
