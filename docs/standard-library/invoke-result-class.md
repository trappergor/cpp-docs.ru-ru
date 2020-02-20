---
title: Класс invoke_result
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: a5f67935bde103cf10c1bd9948ac1388f5221322
ms.sourcegitcommit: f38f770bfda1c174d2b81fabda7c893b15bd83a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77473882"
---
# <a name="invoke_result-class"></a>Класс invoke_result

Определяет тип возвращаемого значения вызываемого типа, который принимает указанные типы аргументов во время компиляции. Добавлено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<class Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Параметры

*Вызываемый*\
Вызываемый тип для запроса.

*Args*\
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Примечания

Используйте этот шаблон, чтобы определить тип результата *вызываемого*(*args*...) во время компиляции, где *вызываемый* объект и все типы в *args* — это любой полный тип, массив неизвестной привязки или, возможно, `void`с квалификатором КП. `type` член шаблона класса называет тип возвращаемого значения, *вызываемого* при вызове с помощью аргументов *args*.... Элемент `type` определяется только в том случае, если *вызываемый* метод может быть вызван при вызове с использованием аргументов *args*... в невычисленном контексте. В противном случае шаблон класса не имеет `type`членов, что позволяет SFINAE тесты для определенного набора типов аргументов во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits >

**Пространство имен:** std

## <a name="see-also"></a>См. также:

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
