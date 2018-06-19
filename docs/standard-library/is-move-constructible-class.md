---
title: Класс is_move_constructible | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d87eac720b205560993a7d6995be8a8fe6ad6194
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843526"
---
# <a name="ismoveconstructible-class"></a>Класс is_move_constructible

Проверяет, имеет ли тип конструктор перемещения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Параметры

T тип для вычисления

## <a name="remarks"></a>Примечания

Предикат типа, результатом вычисления которого будет значение true, если тип `T` может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
