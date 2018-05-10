---
title: Класс result_of | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13dcadc87c23e288c7f8c8a7f5bc9752aae5db7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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

`Fn` Вызываемый тип запроса.

`ArgTypes` Типы список аргументов для вызываемого типа для запроса.

## <a name="remarks"></a>Примечания

Используйте этот шаблон, чтобы определить во время компиляции тип результата `Fn`(`ArgTypes`), где `Fn` — вызываемый тип либо ссылка на функцию или вызываемый тип, вызванные с помощью списка аргументов типов в `ArgTypes`. Член `type` класса шаблонов называет тип результата `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, если неоцененное выражение `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` имеет правильный формат. В противном случае класс шаблона не имеет члена `type`. Тип `Fn` и все типы в пакете параметров `ArgTypes` должны быть полными типами, типами `void` или массивами с неизвестной границей.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
