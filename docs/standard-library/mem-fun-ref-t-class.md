---
title: Класс mem_fun_ref_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: d8f5ef05d1bdeec694cdf22d7e7a163478127dfc
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687759"
---
# <a name="mem_fun_ref_t-class"></a>Класс mem_fun_ref_t

Класс адаптера, который позволяет вызывать функцию-член `non_const`, которая не принимает аргументы, как объект унарной функции при инициализации с ссылочным аргументом. Не рекомендуется использовать в C++ 11, удалено в C++ 17.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;
};
```

### <a name="parameters"></a>Параметры

*_Pm* \
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*left* \
Объект, для которого вызывается функция-член *_Pm* .

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Заметки

Шаблон класса хранит копию *_Pm*, которая должна быть указателем на функцию-член класса `Type` в закрытом объекте-члене. Он определяет свою функцию-член `operator()` как возвращающую (**Left**. * `_Pm`) ().

## <a name="example"></a>Пример

Конструктор `mem_fun_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Пример использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).
