---
title: Класс ostrstream | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::ostrstream [C++], freeze
- std::ostrstream [C++], pcount
- std::ostrstream [C++], rdbuf
- std::ostrstream [C++], str
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38c15829d255ab167fad6c26fca30b491f614ac4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ostrstream-class"></a>Класс ostrstream

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class ostrstream : public ostream
```

## <a name="remarks"></a>Примечания

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) или [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[ostrstream](#ostrstream)|Создает объект типа `ostrstream`.|

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

## <a name="freeze"></a>  ostrstream::freeze

Делает буфер потока недоступным для операций с буфером потока.

```cpp
void freeze(bool _Freezeit = true);
```

### <a name="parameters"></a>Параметры

`_Freezeit` Объект `bool` , указывающее, следует ли поток, который должен быть зафиксирован.

### <a name="remarks"></a>Примечания

Функция-член вызывает метод [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*).

### <a name="example"></a>Пример

См. раздел [strstream::freeze](../standard-library/strstreambuf-class.md#freeze) с примером использования **freeze**.

## <a name="ostrstream"></a>  ostrstream::ostrstream

Создает объект типа `ostrstream`.

```cpp
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Параметры

`ptr` Буфер.

`count` Размер буфера в байтах.

`_Mode` Режим входного и выходного буфера. Дополнительные сведения см. в разделе [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

### <a name="remarks"></a>Примечания

Оба конструктора инициализируют базовый класс путем вызова [ostream](../standard-library/ostream-typedefs.md#ostream)(**sb**), где **sb** является сохраненным объектом класса [strstreambuf](../standard-library/strstreambuf-class.md). Первый конструктор также инициализирует **sb** путем вызова `strstreambuf`. Второй конструктор инициализирует базовый класс одним из двух способов:

- Если `_Mode`  &  **ios_base::app**== 0, то `ptr` должен назначить первый элемент массива из `count` элементов. Далее конструктор вызывает `strstreambuf`(`ptr`, `count`, `ptr`).

- В противном случае `ptr` должен назначить первый элемент массива элементов-счетчиков, содержащий строку C, первый элемент которой обозначается `ptr`. Затем конструктор вызывает `strstreambuf`(`ptr`, `count`, `ptr`  +  `strlen`(`ptr`)).

## <a name="pcount"></a>  ostrstream::pcount

Возвращает число элементов, записанных в управляемую последовательность.

```cpp
streamsize pcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов, записанных в управляемую последовательность.

### <a name="remarks"></a>Примечания

Функция-член возвращает [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount).

### <a name="example"></a>Пример

См. раздел [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `pcount`.

## <a name="rdbuf"></a>  ostrstream::rdbuf

Возвращает указатель на объект strstreambuf, связанный с потоком.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект strstreambuf, связанный с потоком.

### <a name="remarks"></a>Примечания

Функция-член возвращает адрес хранимого буфера потока типа **pointer**, указывающий на [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Пример

См. пример использования `rdbuf` в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="str"></a>  ostrstream::str

Вызывает метод [freeze](../standard-library/strstreambuf-class.md#freeze), а затем возвращает указатель на начало управляемой последовательности.

```cpp
char *str();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало управляемой последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str).

### <a name="example"></a>Пример

См. раздел [strstream::str](../standard-library/strstreambuf-class.md#str) с примером использования **str**.

## <a name="see-also"></a>См. также

[ostream](../standard-library/ostream-typedefs.md#ostream)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
