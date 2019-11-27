---
title: Класс mem_fun1_ref_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_ref_t
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
ms.openlocfilehash: 238d6147b2afa5ca3e143bc57aa4892e17d2c869
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687745"
---
# <a name="mem_fun1_ref_t-class"></a>Класс mem_fun1_ref_t

Класс адаптера, который позволяет вызывать функцию-член `non_const`, которая принимает один аргумент, как объект бинарной функции при инициализации с ссылочным аргументом. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;
};
```

### <a name="parameters"></a>Параметры

*_Pm* \
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*left* \
Объект, для которого вызывается функция-член *_Pm* .

*справа* \
Аргумент, присваиваемый *_Pm*.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая бинарная функция.

## <a name="remarks"></a>Заметки

Шаблон класса хранит копию *_Pm*, которая должна быть указателем на функцию-член класса `Type` в закрытом объекте-члене. Он определяет свою функцию-член `operator()` как возвращаемый (**Left**. \* `_Pm`) (**справа**).

## <a name="example"></a>Пример

Конструктор `mem_fun1_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Пример использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).
