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
ms.openlocfilehash: 9494f7ee2508df1971d56c94b929a7212bedb254
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412297"
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

|Функция-член|Описание|
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

*_Freezeit*<br/>
Объект **bool** , указывающее, следует ли поток, который должен быть зафиксирован.

### <a name="remarks"></a>Примечания

Функция-член вызывает метод [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).

### <a name="example"></a>Пример

См. в разделе [strstreambuf::freeze](../standard-library/strstreambuf-class.md#freeze) пример, использующий `freeze`.

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

Функция-член возвращает адрес буфера сохраненного потока типа `pointer` для [strstreambuf](../standard-library/strstreambuf-class.md).

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

См. в разделе [strstreambuf::str](../standard-library/strstreambuf-class.md#str) пример, использующий `str`.

## <a name="strstream"></a>  strstream::strstream

Создает объект типа `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Размер буфера.

*_Mode*<br/>
Режим ввода-вывода буфера. Дополнительные сведения см. в разделе [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*ptr*<br/>
Буфер.

### <a name="remarks"></a>Примечания

Оба конструктора инициализируют базовый класс путем вызова [streambuf](../standard-library/streambuf-typedefs.md#streambuf)( **sb**), где `sb` является сохраненным объектом класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализирует `sb` путем вызова [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode`  &  **ios_base::app**== 0, то *ptr* должен назначить первый элемент массива `count` элементов, а также вызовы конструктора `strstreambuf`( `ptr`, `count`, `ptr`).

- В противном случае *ptr* должен назначить первый элемент массива элементов count, содержащий строку C первый элемент которой обозначается *ptr*, а также вызовы конструктора `strstreambuf`( `ptr`, `count`, `ptr` + `strlen`( `ptr`) ).

## <a name="see-also"></a>См. также

[iostream](../standard-library/istream-typedefs.md#iostream)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
