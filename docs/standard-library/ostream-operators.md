---
title: Операторы &lt;ostream&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ostream/std::operator&lt;&lt;
dev_langs:
- C++
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4819f5b5d5d6a16720bce29dd176fd0eb873014a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955937"
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

*_Ch* символ.

*_Elem* тип элемента.

*_Ostr* A `basic_ostream` объекта.

*STR* строку символов.

*_Tr* символ признаки.

*Val* тип

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

Определяет длину N = `traits_type::` [длина](../standard-library/char-traits-struct.md#length)(`str`) из последовательности, начиная *str*и вставляет последовательность. Если N < `_Ostr.`[width](../standard-library/ios-base-class.md#width), то функция также вставляет повторение из `_Ostr.width` – N символов заполнения. Повторение предшествует последовательности, если (`_Ostr`. [flags](../standard-library/ios-base-class.md#flags) & `adjustfield` != [left](../standard-library/ios-functions.md#left). В противном случае повторение следует за последовательностью. Функция возвращает *_Ostr*.

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

за исключением того, что каждый элемент *_Ch* из последовательности, начиная *str* преобразуется в тип объекта `Elem` путем вызова `_Ostr.` [поместить](../standard-library/basic-ostream-class.md#put)(`_Ostr.` [widen](../standard-library/basic-ios-class.md#widen)(`_Ch`)).

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

за исключением того, что *_Ch* преобразуется в тип объекта `Elem` путем вызова `_Ostr.put`( `_Ostr.widen`( `_Ch`)).

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

(Она не обязательно должна расширять *_Ch* перед его вставкой.)

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

Возвращает `_Ostr` << (`const char *`) `str`.

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

Возвращает `_Ostr` << (`char`) `_Ch`.

Функция-шаблон:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

Возвращает `_Ostr` << (`const char *`) `str`.

Функция-шаблон:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

Возвращает `_Ostr` << (`char`) `_Ch`.

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

[\<ostream>](../standard-library/ostream.md)<br/>
