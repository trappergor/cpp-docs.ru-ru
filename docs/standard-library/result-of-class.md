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
ms.openlocfilehash: f60a3ef6528da33fd1117fc940e961e9fe0987df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185910"
---
# <a name="resultof-class"></a>Класс result_of

Определяет возвращаемый тип вызываемого типа, который принимает заданные типы аргументов. Добавлена в C ++ 14, устаревшим в C ++ 17.

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

Этот шаблон служит для определения во время компиляции тип результата `Fn`(`ArgTypes`), где *Fn* вызываемый тип, ссылка на функцию или ссылку на вызываемый тип, вызванные с помощью списка аргументов типов в  *ArgTypes*. Член `type` класса шаблонов называет тип результата `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, если неоцененное выражение `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` имеет правильный формат. В противном случае класс шаблона не имеет члена `type`. Тип *Fn* и все типы в пакете параметров *ArgTypes* должны быть полными типами **void**, или массивами с неизвестной границей. Не рекомендуется, вместо него используется [invoke_result](invoke-result-class.md) в C ++ 17.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс invoke_result](invoke-result-class.md)<br/>
