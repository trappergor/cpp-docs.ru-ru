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
ms.openlocfilehash: 8cd72e62fcb65209482fd9677afcc2ec83356feb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689521"
---
# <a name="invoke_result-class"></a>Класс invoke_result

Определяет тип возвращаемого значения вызываемого типа, который принимает указанные типы аргументов во время компиляции. Добавлено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Параметры

*Вызываемый* \
Вызываемый тип для запроса.

*Args* \
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Заметки

Используйте этот шаблон, чтобы определить тип результата *вызываемого*(*args*...) во время компиляции, где *вызываемый* объект и все типы в *args* — это любой полный тип, массив неизвестной привязки или, возможно, `void` с квалификатором КП. @No__t_0 член шаблона класса называет тип возвращаемого значения, *вызываемого* при вызове с помощью аргументов *args*.... Элемент `type` определяется только в том случае, если *вызываемый* метод может быть вызван при вызове с использованием аргументов *args*... в невычисленном контексте. В противном случае шаблон класса не имеет `type` членов, что позволяет SFINAE тесты для определенного набора типов аргументов во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[вызвать](functional-functions.md#invoke)
