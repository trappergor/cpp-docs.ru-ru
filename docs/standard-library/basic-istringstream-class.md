---
title: Класс basic_istringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: 6a8ead5f1014e7f750e01988241ab020431312da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376808"
---
# <a name="basic_istringstream-class"></a>Класс basic_istringstream

Описывает объект, который контролирует извлечение элементов и закодированных объектов `Alloc` из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr,**>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Alloc*\
Класс распределителя.

*Elem*\
Тип основного элемента строки.

*Tr*\
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Remarks

Шаблон класса описывает объект, который контролирует извлечение элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem,** **Tr**, `Alloc`>, с элементами типа *Elem*, чьи черты характера определяются классом *Tr*, и элементы которого выделяются распределительом класса *Alloc.* Этот объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_istringstream](#basic_istringstream)|Создает объект типа `basic_istringstream`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Этот тип является синонимом для параметра шаблона `Alloc`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера `pointer` потока типа `Tr` `Alloc` [в basic_stringbuf,](../standard-library/basic-stringbuf-class.md)< `Elem`>.|
|[Ул](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|
|[Своп](#swap)|Меняет местами значения в этом объекте `basic_istringstream` и значения предоставленного объекта.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Назначает значения этому объекту `basic_istringstream` из параметра объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** \<sstream>

**Пространство имен:** std

## <a name="basic_istringstreamallocator_type"></a><a name="allocator_type"></a>basic_istringstream::allocator_type

Этот тип является синонимом для параметра шаблона `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstreambasic_istringstream"></a><a name="basic_istringstream"></a>basic_istringstream::basic_istringstream

Создает объект типа `basic_istringstream`.

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>Параметры

*_mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*Ул*\
Объект типа `basic_string`.

*Правильно*\
Ссылка rvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует базовый`sb`класс, `sb` позвонив [basic_istream](../standard-library/basic-istream-class.md)(), где находится хранимый объект [класса basic_stringbuf,](../standard-library/basic-stringbuf-class.md)< `Elem` `Tr` `Alloc`>. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).

Второй конструктор инициализирует базовый класс путем вызова `basic_istream(sb)`. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).

Третий конструктор инициализирует объект с содержимым *справа,* относился как ссылка на rvalue.

## <a name="basic_istringstreamoperator"></a><a name="op_eq"></a>basic_istringstream:оператор

Назначает значения этому объекту `basic_istringstream` из параметра объекта.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка rvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Remarks

Оператор-член заменяет содержимое объекта с содержимым *права,* рассматривается как присвоение ссылки на rvalue.

## <a name="basic_istringstreamrdbuf"></a><a name="rdbuf"></a>basic_istringstream:rdbuf

Возвращает адрес сохраненного буфера `pointer` потока типа [для](../standard-library/basic-stringbuf-class.md)< basic_stringbuf `Alloc` **Elem,** **Tr,**>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес сохраненного буфера потока `pointer` типа basic_stringbuf< **Elem,** **Tr,** `Alloc`>.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="basic_istringstreamstr"></a><a name="str"></a>basic_istringstream::str

Задает или получает текст в буфере строк без изменения позиции записи.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Параметры

*_Newstr*\
Новая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект класса [basic_string](../standard-library/basic-string-class.md)< **Elem** `Alloc` , **Tr**,>, чья контролируемая последовательность является копией последовательности, контролируемой ** \*этим.**

### <a name="remarks"></a>Remarks

Функция первого члена возвращает [rdbuf](#rdbuf) -> [str.](../standard-library/basic-stringbuf-class.md#str) Функция второго `rdbuf`  -> члена `_Newstr`вызывает **str**().

### <a name="example"></a>Пример

Смотрите [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) для примера, который использует `str`.

## <a name="basic_istringstreamswap"></a><a name="swap"></a>basic_istringstream::swap

Меняет местами значения двух объектов `basic_istringstream`.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Правильно*|Ссылка `lvalue` на объект `basic_istringstream`.|

### <a name="remarks"></a>Remarks

Функция члена обменивает значения этого объекта и значения *права.*

## <a name="see-also"></a>См. также раздел

[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
