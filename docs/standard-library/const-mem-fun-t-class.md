---
title: Класс const_mem_fun_t
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 16169c094e74178f5a2dd67f70bf75c1f3ee8d87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563596"
---
# <a name="constmemfunt-class"></a>Класс const_mem_fun_t

Класс адаптера, который позволяет вызывать функцию-член-константу, не принимающую аргументы, как объект унарной функции при инициализации с ссылочным аргументом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>Параметры

*PM*<br/>
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*Pleft*<br/>
Объект, *Pm* вызывается функция-член.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию *Pm*, который должен быть указателем на функцию-член класса `Type`, в частном члене объекта. Он определяет свою функцию-член `operator()` как возвращающую ( `Pleft`->\* `Pm`)() **const**.

## <a name="example"></a>Пример

Конструктор `const_mem_fun_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
