---
title: Класс istrstream | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
dev_langs:
- C++
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e48e6fcd7da3b1e1c91b4aecb640c02ae4068bf9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855322"
---
# <a name="istrstream-class"></a>Класс istrstream

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Примечания

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [istringstream](../standard-library/sstream-typedefs.md#istringstream) или [wistringstream](../standard-library/sstream-typedefs.md#wistringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[istrstream](#istrstream)|Создает объект типа `istrstream`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|
|[str](#str)|Вызывает метод [freeze](../standard-library/strstreambuf-class.md#freeze), а затем возвращает указатель на начало управляемой последовательности.|

## <a name="requirements"></a>Требования

**Заголовок:** \<strstream>

**Пространство имен:** std

## <a name="istrstream"></a>  istrstream::istrstream

Создает объект типа `istrstream`.

```cpp
explicit istrstream(
    const char* ptr);

explicit istrstream(
    char* ptr);

istrstream(
    const char* ptr,
    streamsize count);

istrstream(
    char* ptr,
    int count);
```

### <a name="parameters"></a>Параметры

`count` Длина буфера ( `ptr`).

`ptr` Содержимое, с помощью которых буфер инициализации.

### <a name="remarks"></a>Примечания

Все конструкторы инициализируют базовый класс путем вызова [istream](../standard-library/istream-typedefs.md#istream)( **sb**), где **sb** является сохраненным объектом класса [strstreambuf](../standard-library/strstreambuf-class.md). Первые два конструктора также инициализируют **sb** путем вызова `strstreambuf`( ( **const**`char` \*) `ptr`, 0 ). Оставшиеся два конструктора вместо этого вызывают `strstreambuf`( ( **const**`char` *) `ptr`, `count` ).

## <a name="rdbuf"></a>  istrstream::rdbuf

Возвращает указатель на объект strstreambuf, связанный с потоком.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект strstreambuf, связанный с потоком.

### <a name="remarks"></a>Примечания

Функция-член возвращает адрес хранимого буфера потока типа pointer, указывающий на [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Пример

См. раздел [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount) с примером использования `rdbuf`.

## <a name="str"></a>  istrstream::str

Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.

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

[istream](../standard-library/istream-typedefs.md#istream)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
