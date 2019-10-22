---
title: Класс pointer_to_unary_function
ms.date: 02/21/2019
f1_keywords:
- functional/std::pointer_to_unary
helpviewer_keywords:
- pointer_to_unary_function function
- pointer_to_unary_function class
ms.assetid: 05600207-b916-4759-beca-6b6facd2d6f6
ms.openlocfilehash: 2b6bf82faa39e22c5af584a9fc3ebf68f5851463
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689141"
---
# <a name="pointer_to_unary_function-class"></a>Класс pointer_to_unary_function

Преобразует указатель на унарную функцию в адаптируемую унарную функцию. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Arg, class Result>
class pointer_to_unary_function
    : public unary_function<Arg, Result>
{
    explicit pointer_to_unary_function(Result(*pfunc)(Arg));
    Result operator()(Arg left) const;
};
```

### <a name="parameters"></a>Параметры

*pfunc* \
Бинарная функция для преобразования.

*left* \
Объект, для которого вызывается функция *\*pfunc*.

## <a name="return-value"></a>Возвращаемое значение

Шаблон класса хранит копию `pfunc`. Он определяет свою функцию-член `operator()` как возвращающую ( \* **pfunc**)(_ *Left*).

## <a name="remarks"></a>Заметки

Указатель на унарную функцию является объектом функции и может передаваться в любой алгоритм стандартной библиотеки C++, ожидающий унарную функцию в качестве параметра, но не может настраиваться. Чтобы использовать его с адаптером, например привязать к нему значение или использовать его с отрицанием, он должен быть передаваться с вложенными типами `argument_type` и `result_type`, что делает такую адаптацию допустимой. Преобразование посредством `pointer_to_unary_function` позволяет адаптерам функций работать с указателями бинарных функций.

## <a name="example"></a>Пример

Конструктор `pointer_to_unary_function` редко используется напрямую. См. раздел по вспомогательной функции [ptr_fun](../standard-library/functional-functions.md#ptr_fun) с примером того, как объявлять и использовать предикат адаптера `pointer_to_unary_function`.
