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
ms.openlocfilehash: 2b2051b0c854151cff9b439f5ec0a951c25a6387
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447641"
---
# <a name="invokeresult-class"></a>Класс invoke_result

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

*Предназначен*\
Вызываемый тип для запроса.

*Args*\
Типы списка аргументов к вызываемому типу для запроса.

## <a name="remarks"></a>Примечания

Используйте этот шаблон для определения типа результата вызываемого (*args*...) во время компиляции, где *вызываемый* объект и все типы в аргументах *args* являются полным типом, массивом неизвестной привязки или, `void`возможно, с указанием ОПС. Член класса шаблона называет тип возвращаемого значения *Invoke при* вызове с помощью аргументов args....  `type` Элемент определен только в том случае, если вызываемый метод можно вызвать при помощи аргументов *args*...  `type` в невычисленном контексте. В противном случае класс шаблона не имеет `type`члена, что позволяет SFINAE тесты для определенного набора типов аргументов во время компиляции.

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[вызвать](functional-functions.md#invoke)
