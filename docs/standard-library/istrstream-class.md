---
title: Класс istrstream
ms.date: 11/04/2016
f1_keywords:
- strstream/std::istrstream::rdbuf
- strstream/std::istrstream::str
helpviewer_keywords:
- istrstream class
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
ms.openlocfilehash: d548a8c2c47a5a345be725afdedb47524344f720
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337526"
---
# <a name="istrstream-class"></a>Класс istrstream

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class istrstream : public istream
```

## <a name="remarks"></a>Remarks

Объект сохраняет объект класса `strstreambuf`.

> [!NOTE]
> Этот класс устарел. Вместо него рекомендуется использовать [istringstream](../standard-library/sstream-typedefs.md#istringstream) или [wistringstream](../standard-library/sstream-typedefs.md#wistringstream).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[istrstream](#istrstream)|Создает объект типа `istrstream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает указатель на объект `strstreambuf`, связанный с потоком.|
|[Ул](#str)|Вызывает [freeze](../standard-library/strstreambuf-class.md#freeze), затем возвращает указатель на начало управляемой последовательности.|

## <a name="requirements"></a>Требования

**Заголовок:** \<strstream>

**Пространство имен:** std

## <a name="istrstreamistrstream"></a><a name="istrstream"></a>istrstream::istrstream

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

*Рассчитывать*\
Длина буфера *(ptr*).

*Ptr*\
Содержимое, с которым инициализируется буфер.

### <a name="remarks"></a>Remarks

Все конструкторы инициализируют базовый класс, позвонив [в istream](../standard-library/istream-typedefs.md#istream)**(sb),** где `sb` хранится объект класса [strstreambuf.](../standard-library/strstreambuf-class.md) Первые два конструктора также `sb` инициализировать по `ptr`телефону`char` \* `strstreambuf` **(Конст** ) , 0 ). Остальные два конструктора вместо `strstreambuf`вызова (конст) **const** `char` , `ptr` `count` ).

## <a name="istrstreamrdbuf"></a><a name="rdbuf"></a>istrstream::rdbuf

Возвращает указатель на объект strstreambuf, связанный с потоком.

```cpp
strstreambuf *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект strstreambuf, связанный с потоком.

### <a name="remarks"></a>Remarks

Функция-член возвращает адрес хранимого буфера потока типа pointer, указывающий на [strstreambuf](../standard-library/strstreambuf-class.md).

### <a name="example"></a>Пример

См. пример использования `rdbuf` в разделе [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).

## <a name="istrstreamstr"></a><a name="str"></a>istrstream::str

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

[Istream](../standard-library/istream-typedefs.md#istream)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
