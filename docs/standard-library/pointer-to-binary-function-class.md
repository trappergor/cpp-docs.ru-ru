---
title: Класс pointer_to_binary_function
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_binary
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
ms.openlocfilehash: 890ebb7d4c2b8fbd51a4460e21efba3e763ead7e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687195"
---
# <a name="pointer_to_binary_function-class"></a>Класс pointer_to_binary_function

Преобразует указатель на бинарную функцию в адаптируемую бинарную функцию. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Параметры

*pfunc* \
Бинарная функция для преобразования.

*left* \
Левый объект, для которого вызывается функция *\*pfunc*.

*справа* \
Правый объект, для которого вызывается функция *\*pfunc*.

## <a name="return-value"></a>Возвращаемое значение

Шаблон класса хранит копию `pfunc`. Он определяет свою функцию члена `operator()` как возвращаемый `(* pfunc)(Left, right)`.

## <a name="remarks"></a>Заметки

Указатель на бинарную функцию является объектом функции и может передаваться в любой алгоритм стандартной библиотеки C++, ожидающий бинарную функцию в качестве параметра, но не может настраиваться. Чтобы использовать его с адаптером, например привязать к нему значение или использовать его с отрицанием, он должен быть передаваться с вложенными типами `first_argument_type`, `second_argument_type` и `result_type`, что делает такую адаптацию допустимой. Преобразование посредством `pointer_to_binary_function` позволяет адаптерам функций работать с указателями бинарных функций.

## <a name="example"></a>Пример

Конструктор `pointer_to_binary_function` редко используется напрямую. См. раздел по вспомогательной функции [ptr_fun](../standard-library/functional-functions.md#ptr_fun) с примером того, как объявлять и использовать предикат адаптера `pointer_to_binary_function`.
