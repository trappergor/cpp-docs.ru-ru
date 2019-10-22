---
title: Класс const_mem_fun1_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 1af44635400037c6359b13c4f2925c3ac7f2d9d5
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689748"
---
# <a name="const_mem_fun1_t-class"></a>Класс const_mem_fun1_t

Класс адаптера, который позволяет вызывать функцию-член **const**, принимающую один аргумент, как объект бинарной функции при инициализации с аргументом указателя. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>Параметры

*member_ptr* \
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*left* \
Объект **const** , для которого вызывается функция-член *member_ptr* .

*справа* \
Аргумент, присваиваемый *member_ptr*.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая бинарная функция.

## <a name="remarks"></a>Заметки

Шаблон класса хранит копию *member_ptr*, которая должна быть указателем на функцию-член класса `Type` в закрытом объекте-члене. Он определяет свою функцию члена `operator()` как возвращаемый `(left->member_ptr)(right) const`.

## <a name="example"></a>Пример

Конструктор `const_mem_fun1_t` редко используется напрямую. `mem_fn` используется для адаптации функций-членов. Пример использования адаптеров функций элементов см. в разделе [mem_fn](../standard-library/functional-functions.md#mem_fn) .
