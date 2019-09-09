---
title: Операторы &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: c80abcb08423b4bb269e7d60ac43ef97d197a0e9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453521"
---
# <a name="ltostreamgt-operators"></a>Операторы &lt;ostream&gt;

||
|-|
|[operator&lt;&lt;](#op_lt_lt)|

## <a name="op_lt_lt"></a> operator&lt;&lt;

Записывает в поток различные типы.

```cpp
template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const Elem* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    Elem _Ch);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const char* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);

template <class _Elem, class _Tr, class T>
basic_ostream <_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>&& _Ostr,
    Ty val);
```

### <a name="parameters"></a>Параметры

*_Ch*\
Символ.

*_Elem*\
Тип элемента.

*_Ostr*\
Объект `basic_ostream`.

*str*\
Строка символов.

*_Tr*\
Признаки символа.

*Val*\
Тип.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Примечания

Класс `basic_ostream` также определяет несколько операторов вставки. Дополнительные сведения см. в разделе [basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Функция-шаблон

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

Определяет длину последовательности N = `traits_type::` [length](../standard-library/char-traits-struct.md#length)(`str`), начиная с *str*, и вставляет последовательность. Если N < `_Ostr.`[width](../standard-library/ios-base-class.md#width), то функция также вставляет повторение из `_Ostr.width` – N символов заполнения. Повторение предшествует последовательности, если (`_Ostr`. [flags](../standard-library/ios-base-class.md#flags) & `adjustfield` != [left](../standard-library/ios-functions.md#left). В противном случае повторение следует за последовательностью. Функция возвращает *_Ostr*.

Функция-шаблон

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

вставляет элемент `_Ch`. Если 1 < `_Ostr.width`, то функция также вставляет повторение из `_Ostr.width` – 1 символов заполнения. Повторение предшествует последовательности, если `_Ostr.flags & adjustfield != left`. В противном случае повторение следует за последовательностью. Он возвращает *_Ostr*.

Функция-шаблон

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```

ведет себя так же, как

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

за исключением того, что каждый элемент, *_Ch* последовательности, начинающейся с *str* , преобразуется в `_Ostr.`объект типа`_Ostr.` `Elem` `_Ch`путем вызова метода [помещает](../standard-library/basic-ostream-class.md#put)([Widening](../standard-library/basic-ios-class.md#widen)()).

Функция-шаблон

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    char _Ch);
```

ведет себя так же, как

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

за исключением того, что *_Ch* преобразуется в `Elem` объект типа `_Ostr.put`путем `_Ostr.widen`вызова `_Ch`(()).

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```

ведет себя так же, как

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

(Она не обязательно должна расширять элементы перед их вставкой.)

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```

ведет себя так же, как

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

(Не нужно расширять *_Ch* перед вставкой.)

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

Возвращает `_Ostr` < < (`const char *`) `str`.

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

Возвращает `_Ostr` < < (`char`) `_Ch`.

Функция-шаблон:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

Возвращает `_Ostr` < < (`const char *`) `str`.

Функция-шаблон:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

Возвращает `_Ostr` < < (`char`) `_Ch`.

Функция-шаблон:

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

возвращает `_Ostr` `<<` `val` (и в процессе преобразует [ссылку RValue](../cpp/rvalue-reference-declarator-amp-amp.md) в `_Ostr` на lvalue).

### <a name="example"></a>Пример

См. раздел [flush](../standard-library/ostream-functions.md#flush) с примером использования `operator<<`.

## <a name="see-also"></a>См. также

[\<ostream>](../standard-library/ostream.md)
