---
title: Класс const_mem_fun_ref_t
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_ref_t
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
ms.openlocfilehash: 16025764cdcf28900c30ef53dced871998f8bd07
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006582"
---
# <a name="constmemfunreft-class"></a>Класс const_mem_fun_ref_t

Класс адаптера, который позволяет вызывать функцию-член **const**, не принимающую аргументы, как объект унарной функции при инициализации с ссылочным аргументом. Рекомендуется использовать в C ++ 11, удалено в C ++ 17.

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

*PM*<br/>
Указатель на функцию-член класса `Type` для преобразования в объект функции.

*left*<br/>
Объект, *Pm* вызывается функция-член.

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
