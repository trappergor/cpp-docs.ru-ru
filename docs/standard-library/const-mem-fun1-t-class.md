---
title: Класс const_mem_fun1_t | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5fe5c06dd3017e867e73cf1107e619ec2c1edaf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843799"
---
# <a name="constmemfun1t-class"></a>Класс const_mem_fun1_t

Класс адаптера, который позволяет вызывать функцию-член **const**, принимающую один аргумент, как объект бинарной функции при инициализации с аргументом указателя.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t
 : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* _Pm)(Arg) const);
    Result operator()(const Type* _Pleft, Arg right) const;
 };
```

### <a name="parameters"></a>Параметры

`_Pm` Указатель на функцию-член класса **типа** для преобразования в объект функции.

`_Pleft` **Const** объекта, `_Pm` в вызове функции-члена.

`right` Аргумент, который предоставляется для `_Pm`.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая бинарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет в частном члене объекта копию `_Pm`, которая должна быть указателем на функцию-член класса **Type**. Он определяет его функции-члена `operator()` как возвращающий ( **_Pleft**->\* *Pm)(***право**) **const**.

## <a name="example"></a>Пример

Конструктор `const_mem_fun1_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
