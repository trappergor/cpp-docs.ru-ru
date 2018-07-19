---
title: Класс const_mem_fun_ref_t | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5051fe82a4d197a1518ccf9c0f3c797108c665e0
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961253"
---
# <a name="constmemfunreft-class"></a>Класс const_mem_fun_ref_t

Класс адаптера, который позволяет вызывать функцию-член **const**, не принимающую аргументы, как объект унарной функции при инициализации с ссылочным аргументом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type>
class const_mem_fun_ref_t
 : public unary_function<Type, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type& left) const;
 };
```

### <a name="parameters"></a>Параметры

*PM* указатель на функцию-член класса `Type` для преобразования в объект функции.

*слева* объекта, *Pm* вызывается функция-член.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию *Pm*, который должен быть указателем на функцию-член класса `Type`, в частном члене объекта. Он определяет свою функцию-член `operator()` как возвращающую ( **левой**.\* `Pm`) () **const**.

## <a name="example"></a>Пример

Конструктор `const_mem_fun_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Пример использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
