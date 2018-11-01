---
title: Класс wstring_convert
ms.date: 11/04/2016
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
ms.openlocfilehash: df3b003289dcd86e8033521d8cb0cacdbb7dfbd8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636960"
---
# <a name="wstringconvert-class"></a>Класс wstring_convert

Класс шаблона `wstring_convert` выполняет преобразование между строкой двухбайтовых символов и строкой байтовых символов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>Параметры

*codecvt*<br/>
Аспект [языкового стандарта](../standard-library/locale-class.md), представляющий объект преобразования.

*Elem*<br/>
Тип двухбайтового элемента.

## <a name="remarks"></a>Примечания

Класс шаблона описывает объект, управляющий преобразованием между объектами двухбайтовых строк класса `std::basic_string<Elem>` и объектов однобайтовых строк класса `std::basic_string<char>` (они также называются `std::string`). Класс шаблона определяет типы `wide_string` и `byte_string` как синонимы для этих двух типов. Преобразование между последовательностями значений `Elem` (хранятся в объекте `wide_string`) и многобайтовыми последовательностями (хранятся в объекте `byte_string`) выполняется объектом класса `Codecvt<Elem, char, std::mbstate_t>`, который соответствует требованиям аспекта стандартного преобразования кода `std::codecvt<Elem, char, std::mbstate_t>`.

Объект этого класса шаблона сохраняет:

- Однобайтовую строку для отображения при ошибках

- Двухбайтовую строку для отображения при ошибках

- Указатель на назначенный объект преобразования (высвобождается при уничтожении объекта wbuffer_convert)

- Объект состояния для преобразования типа [state_type](#state_type)

- Счетчик преобразований

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[wstring_convert](#wstring_convert)|Создает объект типа `wstring_convert`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[byte_string](#byte_string)|Тип, представляющий однобайтную строку.|
|[wide_string](#wide_string)|Тип, представляющий двухбайтную строку.|
|[state_type](#state_type)|Тип, представляющий состояние преобразования.|
|[int_type](#int_type)|Тип, представляющий целое число.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[from_bytes](#from_bytes)|Преобразует строку однобайтовых символов в строку двухбайтовых символов.|
|[to_bytes](#to_bytes)|Преобразует двухбайтовую строку в однобайтовую.|
|[converted](#converted)|Возвращает количество успешных преобразований.|
|[state](#state)|Возвращает объект, представляющий состояние преобразования.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="byte_string"></a>  wstring_convert::byte_string

Тип, представляющий однобайтную строку.

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::basic_string<char>`.

## <a name="converted"></a>  wstring_convert::converted

Возвращает количество успешных преобразований.

```cpp
size_t converted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число успешных преобразований.

### <a name="remarks"></a>Примечания

Число успешных преобразований хранится в объекте счетчика преобразований.

## <a name="from_bytes"></a>  wstring_convert::from_bytes

Преобразует строку однобайтовых символов в строку двухбайтовых символов.

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Byte*|Последовательность одноэлементных байт для преобразования.|
|*ptr*|Последовательность символов в стиле С, оканчивающаяся нулем, для преобразования.|
|*BSTR*|Строка [byte_string](#byte_string) для преобразования.|
|*Первый*|Первый символ в диапазоне символов для преобразования.|
|*последний*|Последний символ в диапазоне символов для преобразования.|

### <a name="return-value"></a>Возвращаемое значение

Объект строки двухбайтовых символов, полученный в результате преобразования.

### <a name="remarks"></a>Примечания

Если [состояние преобразования](../standard-library/wstring-convert-class.md) объект был *не* создан с явным значением, ему присваивается значение по умолчанию (начальное состояние преобразования) перед началом преобразования. В противном случае он остается неизменным.

Количество успешно преобразованных входных элементов сохраняется в объекте счетчика преобразования. При отсутствии ошибок преобразования функция-член возвращает преобразованную двухбайтовую строку. В противном случае, если объект был создан с помощью инициализатора сообщения об ошибке в двухбайтовой строке, функция-член возвращает объект сообщения об ошибке в двухбайтовой строке. В противном случае функция-член создает объект класса [range_error](../standard-library/range-error-class.md).

## <a name="int_type"></a>  wstring_convert::int_type

Тип, представляющий целое число.

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `wide_string::traits_type::int_type`.

## <a name="state"></a>  wstring_convert::state

Возвращает объект, представляющий состояние преобразования.

```cpp
state_type state() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [состояния преобразования](../standard-library/wstring-convert-class.md), который представляет состояние преобразования.

### <a name="remarks"></a>Примечания

## <a name="state_type"></a>  wstring_convert::state_type

Тип, представляющий состояние преобразования.

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Примечания

Тип описывает объект, который может представлять состояние преобразования. Тип является синонимом `Codecvt::state_type`.

## <a name="to_bytes"></a>  wstring_convert::to_bytes

Преобразует двухбайтовую строку в однобайтовую.

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Char*|Расширенный символ для преобразования.|
|*Wptr*|Последовательность в стиле C, оканчивающаяся нулем, начинающаяся с `wptr`, для преобразования.|
|*Wstr*|Строка [wide_string](#wide_string) для преобразования.|
|*Первый*|Первый элемент в диапазоне преобразуемых элементов.|
|*последний*|Последний элемент в диапазоне преобразуемых элементов.|

### <a name="remarks"></a>Примечания

Если [состояние преобразования](../standard-library/wstring-convert-class.md) объект был *не* создан с явным значением, ему присваивается значение по умолчанию (начальное состояние преобразования) перед началом преобразования. В противном случае он остается неизменным.

Число успешно преобразованных входных элементов сохраняется в объекте счетчика преобразований. При отсутствии ошибок преобразования, функция-член возвращает преобразованную однобайтовую строку. В противном случае, если объект был создан с помощью инициализатора сообщения об ошибке в однобайтовой строке, функция-член возвращает объект сообщения об ошибке в однобайтовой строке. В противном случае функция-член создает объект класса [range_error](../standard-library/range-error-class.md).

## <a name="wide_string"></a>  wstring_convert::wide_string

Тип, представляющий двухбайтную строку.

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::basic_string<Elem>`.

## <a name="wstring_convert"></a>  wstring_convert::wstring_convert

Создает объект типа `wstring_convert`.

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*\*Pcvt*|Объект типа `Codecvt` для выполнения преобразования.|
|*_State*|Объект типа [state_type](#state_type), представляющий состояние преобразования.|
|*_Berr*|Объект [byte_string](#byte_string) для отображения ошибок.|
|*Werr*|Объект [wide_string](#wide_string) для отображения ошибок.|

### <a name="remarks"></a>Примечания

Первый конструктор сохраняет *Pcvt_arg* в [объекте преобразования](../standard-library/wstring-convert-class.md)
