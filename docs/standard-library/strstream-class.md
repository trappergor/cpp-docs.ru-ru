---
title: Класс strstream
ms.date: 11/04/2016
f1_keywords:
- strstream/std::strstream::freeze
- strstream/std::strstream::pcount
- strstream/std::strstream::rdbuf
- strstream/std::strstream::str
helpviewer_keywords:
- std::strstream [C++], freeze
- std::strstream [C++], pcount
- std::strstream [C++], rdbuf
- std::strstream [C++], str
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
ms.openlocfilehash: 53baa350121796d5198211e1fdb08f4341df6b80
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459101"
---
# <a name="strstream-class"></a>Класс strstream

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Примечания

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [stringstream](../standard-library/sstream-typedefs.md#stringstream) или [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[strstream](#strstream)|Создает объект типа `strstream`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[freeze](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|
|[str](#str)|Вызывает метод [freeze](../standard-library/strstreambuf-class.md#freeze), а затем возвращает указатель на начало управляемой последовательности.|

## <a name="requirements"></a>Требования

**Заголовок:** \<strstream>

**Пространство имен:** std

## <a name="freeze"></a>  strstream::freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

*_Freezeit*\
**Логическое** значение, указывающее, нужно ли заморозить поток.

### <a name="remarks"></a>Примечания

Функция-член вызывает метод [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).

### <a name="example"></a>Пример

Пример, в котором используется `freeze`, см. в разделе [strstreambuf:: Freeze](../standard-library/strstreambuf-class.md#freeze) .

## <a name="pcount"></a>  strstream::pcount

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Примечания

Функция-член возвращает [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).

### <a name="example"></a>Пример

См. пример использования метода pcount в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="rdbuf"></a>  strstream::rdbuf

Возвращает указатель на объект strstreambuf, связанный с потоком.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект strstreambuf, связанный с потоком.

### <a name="remarks"></a>Примечания

Функция члена возвращает адрес буфера сохраненного потока типа `pointer` в [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Пример

См. пример использования `rdbuf` в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="str"></a>  strstream::str

Вызывает метод [freeze](../standard-library/strstreambuf-class.md#freeze), а затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Пример

Пример, в котором используется `str`, см. в разделе [strstreambuf:: str](../standard-library/strstreambuf-class.md#str) .

## <a name="strstream"></a>  strstream::strstream

Создает объект типа `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*расчета*\
Размер буфера.

*_Mode*\
Режим ввода-вывода буфера. Дополнительные сведения см. в разделе [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*указатель*\
Буфер.

### <a name="remarks"></a>Примечания

Оба конструктора инициализируют базовый класс путем вызова [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **SB**), где `sb` — это хранимый объект класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализируется `sb` путем вызова [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode` `strstreambuf` `ptr` `count` `count` `ptr`  ios_base:: App = = 0, то PTR должен обозначать первый элемент массива элементов, а конструктор вызывает (,,).  &  .

- В противном случае *ptr* должен обозначать первый элемент массива элементов count, содержащий строку C, первый элемент которой обозначен указателем *ptr*, а `strstreambuf`конструктор вызывает ( `ptr`,, `ptr` `count`  +  `strlen`( `ptr`) ).

## <a name="see-also"></a>См. также

[iostream](../standard-library/istream-typedefs.md#iostream)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
