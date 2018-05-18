---
title: Класс const_mem_fun1_ref_t | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c465ce95ecbf2ecb50e79e6e4cbaafce8cf7a407
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="constmemfun1reft-class"></a>Класс const_mem_fun1_ref_t

Класс адаптера, который позволяет вызывать функцию-член **const**, принимающую один аргумент, как объект бинарной функции при инициализации с ссылочным аргументом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
 : public binary_function<Type, Arg, Result>
 {
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
 };
```

### <a name="parameters"></a>Параметры

`Pm` Указатель на функцию-член класса **типа** для преобразования в объект функции.

`left` **Const** объекта, `Pm` в вызове функции-члена.

`right` Аргумент, который предоставляется для `Pm`.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая бинарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет в частном члене объекта копию `Pm`, которая должна быть указателем на функцию-член класса **Type**. Он определяет функцию-член `operator()` как возвращающую ( `left`.\* *Pm*)( `right`) **const**.

## <a name="example"></a>Пример

Конструктор `const_mem_fun1_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Примеры использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
