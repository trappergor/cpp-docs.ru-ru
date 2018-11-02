---
title: Класс result_of
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
ms.openlocfilehash: 84a0fbc9ecfb1a6ba18a10aafce8cd8e50cd5ec6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563830"
---
# <a name="resultof-class"></a>Класс result_of

Определяет возвращаемый тип вызываемого типа, который принимает заданные типы аргументов.

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

*fn*<br/>
Вызываемый тип для запроса.

*ArgTypes*<br/>
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Примечания

Этот шаблон служит для определения во время компиляции тип результата `Fn`(`ArgTypes`), где *Fn* вызываемый тип, ссылка на функцию или ссылку на вызываемый тип, вызванные с помощью списка аргументов типов в  *ArgTypes*. Член `type` класса шаблонов называет тип результата `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, если неоцененное выражение `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` имеет правильный формат. В противном случае класс шаблона не имеет члена `type`. Тип *Fn* и все типы в пакете параметров *ArgTypes* должны быть полными типами **void**, или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
