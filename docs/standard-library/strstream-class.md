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
ms.openlocfilehash: 047b7e9d7fdece75137980b013d43abf1d5e3ec3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376622"
---
# <a name="strstream-class"></a>Класс strstream

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class strstream : public iostream
```

## <a name="remarks"></a>Remarks

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [stringstream](../standard-library/sstream-typedefs.md#stringstream) или [wstringstream](../standard-library/sstream-typedefs.md#wstringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[strstream](#strstream)|Создает объект типа `strstream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Заморозить](#freeze)|Делает буфер потока недоступным для операций с буфером потока.|
|[pcount](#pcount)|Возвращает число элементов, записанных в управляемую последовательность.|
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|
|[Ул](#str)|Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.|

## <a name="requirements"></a>Требования

**Заголовок:** \<strstream>

**Пространство имен:** std

## <a name="strstreamfreeze"></a><a name="freeze"></a>strstream::freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

*_Freezeit*\
**Bool** с указанием, хотите ли вы, чтобы поток был заморожен.

### <a name="remarks"></a>Remarks

Функция члена вызывает[замораживание](../standard-library/strstreambuf-class.md#freeze) [rdbuf](#rdbuf) -> (яФроит). *Freezeit*

### <a name="example"></a>Пример

См [strstreambuf::заморозить](../standard-library/strstreambuf-class.md#freeze) для `freeze`примера, который использует .

## <a name="strstreampcount"></a><a name="pcount"></a>strstream::pсчет

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Remarks

Функция члена возвращает [rdbuf](#rdbuf) -> [pcount.](../standard-library/strstreambuf-class.md#pcount)

### <a name="example"></a>Пример

См. пример использования метода pcount в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="strstreamrdbuf"></a><a name="rdbuf"></a>strstream::rdbuf

Возвращает указатель на объект strstreambuf, связанный с потоком.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект strstreambuf, связанный с потоком.

### <a name="remarks"></a>Remarks

Функция участника возвращает адрес сохраненного буфера `pointer` потока типа [в strstreambuf.](../standard-library/strstreambuf-class.md)

### <a name="example"></a>Пример

См. пример использования `rdbuf` в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="strstreamstr"></a><a name="str"></a>strstream::str

Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Remarks

Функция члена возвращает [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Пример

Смотрите [strstreambuf::str](../standard-library/strstreambuf-class.md#str) для образца, который использует `str`.

## <a name="strstreamstrstream"></a><a name="strstream"></a>strstream::strstream

Создает объект типа `strstream`.

```cpp
strstream();

strstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*Рассчитывать*\
Размер буфера.

*_mode*\
Режим ввода-вывода буфера. См. раздел [ios_base::openmode](../standard-library/ios-base-class.md#openmode) для получения дополнительной информации.

*Ptr*\
Буфер.

### <a name="remarks"></a>Remarks

Оба конструктора инициализируют базовый класс, вызывая `sb` [streambuf](../standard-library/streambuf-typedefs.md#streambuf) **(sb),** где хранится объект класса [strstreambuf.](../standard-library/strstreambuf-class.md) Первый конструктор также инициализирует, `sb` вызывая [strstreambuf](../standard-library/strstreambuf-class.md#strstreambuf). Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode`  &  **ios_base::app**No 0, то *ptr* должен обозначить первый элемент массива элементов, `count` и конструктор `strstreambuf`вызывает (, `ptr` `count`, `ptr`).

- В противном случае, *ptr* должен обозначить первый элемент массива элементов подсчета, который содержит строку `ptr`  +  `strlen` `ptr`C, первый элемент которого обозначен *ptr,* и вызовы `strstreambuf`конструктора (, `ptr` `count`( ).

## <a name="see-also"></a>См. также раздел

[Iostream](../standard-library/istream-typedefs.md#iostream)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
