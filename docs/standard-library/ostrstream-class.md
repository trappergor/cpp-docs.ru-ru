---
title: Класс ostrstream
ms.date: 11/04/2016
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
ms.openlocfilehash: b52ba70607a5214a6aa28f04cdded0b19a56b2f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373545"
---
# <a name="ostrstream-class"></a>Класс ostrstream

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Remarks

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) или [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[ostrstream](#ostrstream)|Создает объект типа `ostrstream`.|

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

## <a name="ostrstreamfreeze"></a><a name="freeze"></a>ostrstream::заморозка

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

См [strstream::заморозить](../standard-library/strstreambuf-class.md#freeze) для `freeze`примера, который использует .

## <a name="ostrstreamostrstream"></a><a name="ostrstream"></a>ostrstream::ostrstream

Создает объект типа `ostrstream`.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Параметры

*Ptr*\
Буфер.

*Рассчитывать*\
Размер буфера в байтах.

*_mode*\
Режим ввода-вывода буфера. См. раздел [ios_base::openmode](../standard-library/ios-base-class.md#openmode) для получения дополнительной информации.

### <a name="remarks"></a>Remarks

Оба конструктора инициализируют базовый класс, вызывая [ostream](../standard-library/ostream-typedefs.md#ostream)**(sb),** где `sb` хранится объект класса [strstreambuf.](../standard-library/strstreambuf-class.md) Первый конструктор также инициализирует, `sb` вызывая `strstreambuf`. Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode`  &  **ios_base::app**No 0, `ptr` то необходимо обозначить `count` первый элемент массива элементов, `strstreambuf`и конструктор вызывает (,`ptr` `count`, `ptr`).

- В `ptr` противном случае необходимо обозначить первый элемент массива элементов подсчета, содержащий строку C, первый элемент которой обозначен `ptr`, и вызовы `strstreambuf`конструктора`ptr`(, `count` `ptr`  +  `strlen`( ). `ptr`

## <a name="ostrstreampcount"></a><a name="pcount"></a>ostrstream::pсчет

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Remarks

Функция члена возвращает [rdbuf](#rdbuf) -> [pcount.](../standard-library/strstreambuf-class.md#pcount)

### <a name="example"></a>Пример

См. раздел [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `pcount`.

## <a name="ostrstreamrdbuf"></a><a name="rdbuf"></a>ostrstream::rdbuf

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

## <a name="ostrstreamstr"></a><a name="str"></a>ostrstream::str

Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Remarks

Функция члена возвращает [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Пример

Смотрите [strstream::str](../standard-library/strstreambuf-class.md#str) для образца, который использует `str`.

## <a name="see-also"></a>См. также раздел

[Ostream](../standard-library/ostream-typedefs.md#ostream)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
