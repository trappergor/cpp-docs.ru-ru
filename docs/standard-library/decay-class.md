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
ms.openlocfilehash: 7d3ad5bae067bb9661b6cf475d0831b2b2dfcd2a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099529"
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

*T*<br/>
Тип для изменения.

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
