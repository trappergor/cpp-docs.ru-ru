---
title: Класс const_mem_fun_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 0bdfdbac7a23a4b0e3b830b05990bf028c7bb316
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244549"
---
# <a name="constmemfunt-class"></a>Класс const_mem_fun_t

Класс адаптера, который позволяет вызывать функцию-член-константу, не принимающую аргументы, как объект унарной функции при инициализации с ссылочным аргументом. Рекомендуется использовать в C ++ 11, удалено в C ++ 17.

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

*PM*\
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*Pleft*\
Объект, *Pm* вызывается функция-член.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию *Pm*, который должен быть указателем на функцию-член класса `Type`, в частном члене объекта. Он определяет свою функцию-член `operator()` как возвращающую (`Pleft` -> \* `Pm`) () **const**.

## <a name="example"></a>Пример

Конструктор `const_mem_fun_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun`. Пример использования адаптера функции-члена см. в разделе [mem_fun](../standard-library/functional-functions.md#mem_fun).
