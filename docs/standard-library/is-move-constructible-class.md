---
title: Класс is_move_constructible
ms.date: 10/24/2019
f1_keywords:
- type_traits/std::is_move_constructible
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
ms.openlocfilehash: 9585a932a34a24769201aaa379525a9b4c181e41
ms.sourcegitcommit: 33a898bf976c65f998b4e88a84765a0cef4193a8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920092"
---
# <a name="is_move_constructible-class"></a>Класс is_move_constructible

Проверяет, может ли тип быть создан с помощью операции перемещения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Параметры

*T* \
Оцениваемый тип.

## <a name="remarks"></a>Заметки

Предикат типа, который возвращает **значение true** , если тип *T* может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`. Тип *T* , не имеющий конструктора перемещения, но имеющий конструктор копии, принимающий аргумент `const T&`, удовлетворяет `std::is_move_constructible`.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
