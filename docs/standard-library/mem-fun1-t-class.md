---
title: Класс mem_fun1_t | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c90838bf4ae49e372b35ca2e9a2f0feede4eb9b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="memfun1t-class"></a>Класс mem_fun1_t

Класс адаптера, который позволяет вызывать функцию-член **non_const**, принимающую один аргумент, как объект бинарной функции при инициализации с аргументом-указателем.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;

};
```

### <a name="parameters"></a>Параметры

`_Pm` Указатель на функцию-член класса **типа** для преобразования в объект функции.

`_Pleft` Объект, `_Pm` в вызове функции-члена.

`right` Аргумент, который предоставляется для `_Pm`.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая бинарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет в частном члене объекта копию `_Pm`, которая должна быть указателем на функцию-член класса **Type**. Он определяет свою функцию-член `operator()` как возвращающую ( **_Pleft**->\* `_Pm`)( **right**).

## <a name="example"></a>Пример

Конструктор `mem_fun1_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
