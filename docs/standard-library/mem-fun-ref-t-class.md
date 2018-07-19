---
title: Класс mem_fun_ref_t | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc0684d51fd406f16588188555f67fcebb351fbf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956102"
---
# <a name="memfunreft-class"></a>Класс mem_fun_ref_t

Класс адаптера, который позволяет `non_const` функция-член, не принимающую аргументы как объект унарной функции при инициализации с ссылочным аргументом.

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

*_Pm* указатель на функцию-член класса `Type` для преобразования в объект функции.

*слева* объекта, *_Pm* вызывается функция-член.

## <a name="return-value"></a>Возвращаемое значение

Адаптируемая унарная функция.

## <a name="remarks"></a>Примечания

Класс шаблона сохраняет копию *_Pm*, который должен быть указателем на функцию-член класса `Type`, в частном члене объекта. Он определяет свою функцию-член `operator()` как возвращающую ( **left**.* `_Pm`)( ).

## <a name="example"></a>Пример

Конструктор `mem_fun_ref_t` обычно не используется напрямую; для адаптации функций-членов используется вспомогательная функция `mem_fun_ref`. Пример использования адаптеров функций-членов см. в разделе [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)<br/>
