---
title: Класс const_mem_fun_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 5263612a26b2bcb606ad712a2a8e0a521ce9437a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688205"
---
# <a name="const_mem_fun_t-class"></a>Класс const_mem_fun_t

Класс адаптера, который позволяет вызывать функцию-член-константу, не принимающую аргументы, как объект унарной функции при инициализации с ссылочным аргументом. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

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

@No__t_1 *PM*
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*Плефт* \
Объект, для которого вызывается функция-член *PM* .

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Заметки

Шаблон класса хранит копию *PM*, которая должна быть указателем на функцию-член класса `Type` в закрытом объекте-члене. Он определяет свою функцию-член `operator()` как возвращаемое (`Pleft` -> \* `Pm`) () **const**.

## <a name="example"></a>Пример

Конструктор `const_mem_fun_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).
