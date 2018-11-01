---
title: Класс mem_fun_t
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 32c66eb20215bc68efd0f0bb43c30f951da1bae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456372"
---
# <a name="memfunt-class"></a>Класс mem_fun_t

Класс адаптера, который позволяет `non_const` функция-член, не принимающую аргументы как объект унарной функции при инициализации с аргументом указателя.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

};
```

### <a name="parameters"></a>Параметры

*_Pm*<br/>
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*_Pleft*<br/>
Объект, *_Pm* вызывается функция-член.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию *_Pm*, который должен быть указателем на функцию-член класса `Type`, в частном члене объекта. В нем определяется функция-член `operator()` как возвращающая returning ( `_Pleft`->* `_Pm`)( ).

## <a name="example"></a>Пример

Конструктор `mem_fun_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<functional>](../standard-library/functional.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
