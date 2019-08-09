---
title: Класс result_of
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
ms.openlocfilehash: 5a3265cfe4b2629bf02925ea6e3eeb0c4acb1e0e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451213"
---
# <a name="resultof-class"></a>Класс result_of

Определяет возвращаемый тип вызываемого типа, который принимает заданные типы аргументов. Добавлено в C++ 14, не рекомендуется в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>Параметры

*FN*\
Вызываемый тип для запроса.

*аргтипес*\
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Примечания

Используйте этот шаблон для определения во `Fn`время компиляции типа результата (`ArgTypes`), где *fn* — это вызываемый тип, ссылка на функцию или ссылка на вызываемый тип, вызываемая с помощью списка аргументов типов в *аргтипес*. Член `type` класса шаблонов называет тип результата `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, если неоцененное выражение `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` имеет правильный формат. В противном случае класс шаблона не имеет члена `type`. Тип *fn* и все типы в пакете параметров *аргтипес* должны быть полными типами, **void**или массивами неизвестной привязки. Не рекомендуется в пользу [invoke_result](invoke-result-class.md) в c++ 17.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[класс invoke_result](invoke-result-class.md)
