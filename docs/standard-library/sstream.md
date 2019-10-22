---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 3f1fb202692d09fa87eb775677e46e1c3f36dbad
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688943"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

Определяет несколько шаблонов классов, поддерживающих операции iostream для последовательностей, хранящихся в выделенном объекте массива. Такие последовательности легко преобразуются в объекты и из объектов шаблона класса [basic_string](../standard-library/basic-string-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*left*|Ссылка на объект `sstream`.|
|*right*|Ссылка на объект `sstream`.|

## <a name="remarks"></a>Заметки

Объекты типа `char *` могут использовать функциональность объекта [\<strstream>](../standard-library/strstream.md) для потоковой передачи. Однако \<strstream > является устаревшим и рекомендуется использовать \<sstream >.

### <a name="typedefs"></a>Typedefs

|Имя типа|Описание|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Создает тип, `basic_istringstream` специализированный для параметра шаблона **char** .|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Создает тип, `basic_ostringstream` специализированный для параметра шаблона **char** .|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Создает тип, `basic_stringbuf` специализированный для параметра шаблона **char** .|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Создает тип, `basic_stringstream` специализированный для параметра шаблона **char** .|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Создает тип, `basic_istringstream` специализированный для параметра шаблона **wchar_t** .|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Создает тип, `basic_ostringstream` специализированный для параметра шаблона **wchar_t** .|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Создает тип, `basic_stringbuf` специализированный для параметра шаблона **wchar_t** .|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Создает тип, `basic_stringstream` специализированный для параметра шаблона **wchar_t** .|

### <a name="manipulators"></a>Манипуляторы

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|Меняет местами значения двух объектов `sstream`.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|Описывает буфер потока, который управляет передачей элементов типа `Elem`, признаки символов которого определяются с помощью класса `Tr`, в последовательность элементов, сохраненную в объекте массива, и из нее.|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**Elem**, **tr**`Alloc` > с элементами типа `Elem`, признаки символов которых определяются класс `Tr`, элементы которого выделяются распределителем класса `Alloc`.|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**Elem**, **tr**`Alloc` > с элементами типа `Elem`, признаки символов которых определяются свойством класс `Tr`, элементы которого выделяются распределителем класса `Alloc`.|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <**Elem**, **tr**`Alloc` > с элементами типа `Elem`, признаки символов которых определяется классом `Tr`, элементы которого выделяются распределителем класса `Alloc`.|

## <a name="requirements"></a>Требования

- **Заголовок:** \<sstream>

- **Пространство имен:** std

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
