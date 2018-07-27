---
title: Класс pointer_to_binary_function | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b632fabe8f596d46a0423d670ff57bb12de93cd
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953460"
---
# <a name="pointertobinaryfunction-class"></a>Класс pointer_to_binary_function

Преобразует указатель на бинарную функцию в адаптируемую бинарную функцию.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```

### <a name="parameters"></a>Параметры

*pfunc* бинарная функция для преобразования.

*слева* левый объект,  *\*pfunc* вызывается.

*правом* правый объект,  *\*pfunc* вызывается.

## <a name="return-value"></a>Возвращаемое значение

Класс шаблона сохраняет копию `pfunc`. Он определяет свою функцию-член `operator()` как возвращающую (\* **pfunc**)(_ *Left*, \_ *Right*).

## <a name="remarks"></a>Примечания

Указатель на бинарную функцию является объектом функции и может передаваться в любой алгоритм стандартной библиотеки C++, ожидающий бинарную функцию в качестве параметра, но не может настраиваться. Для использования его с адаптером, например привязка к нему значения или использование его с negator, он должен передаваться с вложенными типами `first_argument_type`, `second_argument_type`, и `result_type` , делает такую возможных. Преобразование посредством `pointer_to_binary_function` позволяет адаптерам функций работать с указателями бинарных функций.

## <a name="example"></a>Пример

Конструктор `pointer_to_binary_function` редко используется напрямую. См. раздел по вспомогательной функции [ptr_fun](../standard-library/functional-functions.md#ptr_fun) с примером того, как объявлять и использовать предикат адаптера `pointer_to_binary_function`.

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
