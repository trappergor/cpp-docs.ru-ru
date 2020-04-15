---
title: Операторы &lt;ostream&gt;
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: d8b6f4e0f0b5bca41f8d895415fff4003231ad1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373608"
---
# <a name="ltostreamgt-operators"></a>Операторы &lt;ostream&gt;

||
|-|
|[Оператор&lt;&lt;](#op_lt_lt)|

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Оператор&lt;&lt;

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

*_ch*\
Символ.

*_Elem*\
Тип элемента.

*_ostr*\
Объект `basic_ostream` .

*Ул*\
Строка символов.

*_Tr*\
Признаки символа.

*Валь*\
Тип.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Remarks

Класс `basic_ostream` также определяет несколько операторов вставки. Для получения дополнительной информации [см.&lt;basic_ostream::оператор](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt).

Функция-шаблон

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

определяет длину N `traits_type::`и`str` [длины](../standard-library/char-traits-struct.md#length)( ) последовательности, начинающаяся в *str,* и вставляет последовательность. Если N < `_Ostr.`[width](../standard-library/ios-base-class.md#width), то функция также вставляет повторение из `_Ostr.width` – N символов заполнения. Повторение предшествует`_Ostr`последовательности, если ( . [флаги](../standard-library/ios-base-class.md#flags)  &  `adjustfield` ! » [слева](../standard-library/ios-functions.md#left). В противном случае повторение следует за последовательностью. Функция *возвращается _Ostr*.

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

кроме того, что каждый элемент *_Ch* последовательности, `Elem` начинающаяся на *str,* преобразуется в объект типа путем вызова `_Ostr.` [put](../standard-library/basic-ostream-class.md#put)`_Ostr.`[(расширяется](../standard-library/basic-ios-class.md#widen)(`_Ch`)).

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

за *_Ch* исключением того, что `Elem` _Ch `_Ostr.put`преобразуется `_Ch`в объект типа по вызову () `_Ostr.widen`

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

(Он не должен расширять *_Ch* перед вставкой.)

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

возвращает `_Ostr` << ()`const char *` `str`.

Функция-шаблон

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

возвращает `_Ostr` << ()`char` `_Ch`.

Функция-шаблон:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

возвращает `_Ostr` << ()`const char *` `str`.

Функция-шаблон:

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

возвращает `_Ostr` << ()`char` `_Ch`.

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

## <a name="see-also"></a>См. также раздел

[\<ostream>](../standard-library/ostream.md)
