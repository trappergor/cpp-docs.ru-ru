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
ms.openlocfilehash: 7c03240d3ee666fcda30562279a8dbda2ca8dc7b
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006875"
---
# <a name="invokeresult-class"></a>Класс invoke_result

Определяет тип возвращаемого значения вызываемого типа, который принимает указанных типов аргументов во время компиляции. Добавлен в C ++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Параметры

*Вызываемый*<br/>
Вызываемый тип для запроса.

*Args*<br/>
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Примечания

Этот шаблон служит для определения типа результата *Callable*(*Args*...) во время компиляции, где *Callable* и все типы в *Args* любого полного типа, массив неизвестной границей или возможно квалифицированная `void`. `type` Тип возвращаемого значения имен членов класса шаблона *Callable* при вызове с помощью аргументов *Args*... `type` Член определен только в том случае, если *Callable* может вызываться при вызове с помощью аргументов *Args*... в невычисляемом контексте. В противном случае класс шаблона не имеет члена `type`, что позволяет SFINAE тесты на основе определенного набора типов аргументов во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Вызвать](functional-functions.md#invoke)
