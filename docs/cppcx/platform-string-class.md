---
title: Класс Platform::String
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
ms.openlocfilehash: 3f29c60d0d6a4618d97d8f750a048fcc18f976b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322118"
---
# <a name="platformstring-class"></a>Класс Platform::String

Представляет упорядоченную коллекцию символов Юникода, используемую для представления текста. Для получения дополнительной информации и [примеров см.](../cppcx/strings-c-cx.md)

## <a name="syntax"></a>Синтаксис

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Iterators

Две функции итераторов, не являющиеся членами класса String, можно использовать с функциями шаблона `std::for_each` для перечисления символов в объекте String.

|Участник|Описание|
|------------|-----------------|
|`const char16* begin(String^ s)`|Возвращает указатель на начало указанного объекта String.|
|`const char16* end(String^ s)`|Возвращает указатель на позицию после окончания указанного объекта String.|

## <a name="members"></a>Участники

Класс String наследует от класса Object и интерфейсов IDisposable, IEquatable и IPrintable.

Класс String имеет также следующие типы членов.

### <a name="constructors"></a>Конструкторы

|Участник|Описание|
|------------|-----------------|
|[Строка::Строка](#ctor)|Инициализирует новый экземпляр класса String.|

### <a name="methods"></a>Методы

Класс String наследует методы Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() и ToString() от класса [Platform::Object Class](../cppcx/platform-object-class.md). Класс String содержит также следующие методы.

|Метод|Описание|
|------------|-----------------|
|[Строка::Начало](#begin)|Возвращает указатель на начало текущей строки.|
|[Строка::СравнениЕОрдинальный](#compareordinal)|Сравнивает два объекта `String` , оценивая числовые значения соответствующих символов в двух строковых значениях, представленных объектами.|
|[Строка::Concat](#concat)|Объединяет значения двух объектов String.|
|[Строка::Data](#data)|Возвращает указатель на начало текущей строки.|
|[Строка::Dispose](#dispose)|Высвобождает ресурсы.|
|[Строка::Конец](#end)|Возвращает указатель на позицию после конца текущей строки.|
|[Строка::Равные](#equals)|Указывает, равен ли указанный объект текущему объекту.|
|[Строка::GetHashCode](#gethashcode)|Возвращает хэш-код для этого экземпляра.|
|[Строка::Пустой](#isempty)|Указывает, является ли объект String пустым.|
|[Строка::IsFastPass](#isfastpass)|Указывает, участвует ли текущий объект Строки в операции *быстрого прохода.* В операции быстрой передачи подсчет ссылок приостанавливается.|
|[Строка::Длина](#length)|Получает длину текущего объекта String.|
|[Строка::ToString](#tostring)|Возвращает объект String, значение которого совпадает со значением текущей строки.|

### <a name="operators"></a>Операторы

Класс строки имеет следующих операторов.

|Участник|Описание|
|------------|-----------------|
|[Строка::Оператор оператор](#operator-equality)|Указывает, имеют ли два указанных объекта строки одинаковое значение.|
|[Оператор operator+](#operator-plus)|Сцепляет два объекта String в новый объект String.|
|[Строка:Оператор> Оператор](#operator-greater-than)|Указывает, является ли значение одного объекта String большим, чем значение второго объекта String.|
|[Строка::Оператор>- Оператор](#operator-greater-than-or-equals)|Указывает, является ли значение одного объекта String больше или равным значению второго объекта String.|
|[Строка::Оператор!](#operator-inequality)|Указывает, имеют ли два указанных объекта строки разные значения.|
|[Строка:Оператор< Оператор](#operator-less-than)|Указывает, является ли значение одного объекта String меньшим, чем значение второго объекта String.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Заголовок** vccorlib.h (включается по умолчанию)

## <a name="stringbegin-method"></a><a name="begin"></a>Строка::Начало метод

Возвращает указатель на начало текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
char16* Begin();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало текущей строки.

## <a name="stringcompareordinal-method"></a><a name="compareordinal"></a>Строка::СравнениЕОрдинальный метод

Статический метод, `String` который сравнивает два объекта, оценивая числовые значения соответствующих символов в двух значениях строки, представленных объектами.

### <a name="syntax"></a>Синтаксис

```cpp
static int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект String.

*str2*<br/>
Второй объект String.

### <a name="return-value"></a>Возвращаемое значение

Целое число, выражающее лексическое соотношение двух сравниваемых значений. В следующей таблице перечислены возможные возвращаемые значения.

|Значение|Условие|
|-----------|---------------|
|-1|Значение `str1` меньше `str2`.|
|0|Значение `str1` равно значению `str2`.|
|1|Значение `str1` больше значения `str2`.|

## <a name="stringconcat-method"></a><a name="concat"></a>Строка::Метод конката

Объединяет значения двух объектов String.

### <a name="syntax"></a>Синтаксис

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект String или значение `null`.

*str2*<br/>
Второй объект String или значение `null`.

### <a name="return-value"></a>Возвращаемое значение

Новый объект String^, значение которого является объединением значений `str1` и `str2`.

Если `str1` имеет значение `null`, а `str2` — значение, отличное от null, возвращается значение `str1`. Если `str2` имеет значение `null`, а `str1` — значение, отличное от null, возвращается значение `str2`. Если оба параметра `str1` и `str2` имеют значение `null`, возвращается пустая строка (L"").

## <a name="stringdata-method"></a><a name="data"></a>Струна::Dата Метод

Возвращает указатель на начало буфера данных объекта в качестве массива элементов `char16` (`wchar_t`) в стиле языка C.

### <a name="syntax"></a>Синтаксис

```cpp
const char16* Data();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало массива `const char16` символов Unicode`char16` (является typedef для). `wchar_t`

### <a name="remarks"></a>Remarks

Используйте этот метод для преобразования из `Platform::String^` в `wchar_t*`. Когда объект `String` выходит за пределы области, указатель Data больше не является гарантированно допустимым. Для хранения данных за пределами срока службы исходного `String` объекта используйте [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) для копирования массива в память, которую вы выделили самостоятельно.

## <a name="stringdispose-method"></a><a name="dispose"></a>Строка::Dпозамный метод

Высвобождает ресурсы.

### <a name="syntax"></a>Синтаксис

```cpp
virtual override void Dispose();
```

## <a name="stringend-method"></a><a name="end"></a>Строка::Конец метода

Возвращает указатель на позицию после конца текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
char16* End();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на позицию после конца текущей строки.

### <a name="remarks"></a>Remarks

Конец () возвращает Бег() - Длина.

## <a name="stringequals-method"></a><a name="equals"></a>Строка::Равный метод

Указывает, совпадает ли значение заданного объекта String со значением текущего объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `str` равен текущему объекту; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Этот метод эквивалентен статической [строке::СравнениеOrdinal](#compareordinal). В первой перегрузке предполагается, что параметр `str` может быть приведен к объекту String^.

## <a name="stringgethashcode-method"></a><a name="gethashcode"></a>Строка::GetHashCode Метод

Возвращает хэш-код для этого экземпляра.

### <a name="syntax"></a>Синтаксис

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Хэш-код данного экземпляра.

## <a name="stringisempty-method"></a><a name="isempty"></a>Строка::Пустой метод

Указывает, является ли объект String пустым.

### <a name="syntax"></a>Синтаксис

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `String` текущий объект **является нулевым** или пустой строкой (L"); в противном случае, **ложные**.

## <a name="stringisfastpass-method"></a><a name="isfastpass"></a>Строка::Метод IsFastPass

Указывает, участвует ли текущий объект Строки в операции *быстрого прохода.* В операции быстрой передачи подсчет ссылок приостанавливается.

### <a name="syntax"></a>Синтаксис

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `String` текущий объект быстро-прошлое; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

При вызове функции, где в качестве параметра используется объект с подсчетом ссылок и вызываемая функция обращается к этому объекту только для чтения, компилятор может безопасно приостановить подсчет ссылок, чтобы повысить производительность вызова. Это свойство не дает никакой дополнительной пользы для вашего кода. Система обрабатывает все сведения.

## <a name="stringlength-method"></a><a name="length"></a>Строка::Метод длины

Извлекает количество символов в `String` текущем объекте.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Возвращаемое значение

Количество символов в текущем `String` объекте.

### <a name="remarks"></a>Remarks

Длина объекта String без символов равна нулю. Длина следующего объекта String равна 5.

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

Массив символов, возвращенный [String::Data](#data) имеет один дополнительный символ, который является прекращением NULL или 'No0'. Этот символ также имеет длину 2 байта.

## <a name="stringoperator-operator"></a><a name="operator-plus"></a>Строка::Оператор

Конкатирует два [объекта струны](../cppcx/platform-string-class.md) в новый объект [струны.](../cppcx/platform-string-class.md)

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`, содержимое которого будет добавлено в `str1`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если *str1* равен *str2;* в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Этот оператор создает объект `String^`, содержащий данные из двух операндов. Используйте его для удобства, если производительность не играет решающей роли. Несколько вызовов "`+`" в функции, скорее всего, не будут иметь последствий, но если вы имеете дело с большими объектами или текстовыми данными в сложном цикле, используйте стандартные механизмы и типы C++.

## <a name="stringoperator-operator"></a><a name="operator-equality"></a>Строка::Оператор оператор

Указывает, равны ли текстовые значения двух указанных объектов String.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый сравниваемый объект `String`.

*str2*<br/>
Второй сравниваемый объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `str1` содержание `str2`равны; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Этот оператор эквивалентен [String::CompareOrdinal](#compareordinal).

## <a name="stringoperatorgt"></a><a name="operator-greater-than"></a>Строка::оператор&gt;

Указывает, является ли `String` значение одного объекта больше `String` значения второго объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `str1` значение `str2`больше, чем значение; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Этот оператор эквивалентен явному вызову [String::CompareOrdinal](#compareordinal) и получению результата больше нуля.

## <a name="stringoperatorgt"></a><a name="operator-greater-than-or-equals"></a>Строка::оператор&gt;=

Указывает, является ли `String` значение одного объекта больше или равно `String` значению второго объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `str1` значение больше или равно стоимости; `str2` в противном случае, **ложные**.

## <a name="stringoperator"></a><a name="operator-inequality"></a>Строка::оператор!

Указывает, имеют `String` ли два указанных объекта разные значения.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый сравниваемый объект `String`.

*str2*<br/>
Второй сравниваемый объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `str1` не `str2`равна ; в противном случае, **ложные**.

## <a name="stringoperatorlt"></a><a name="operator-less-than"></a>Строка::оператор&lt;

Указывает, меньше значения `String` одного объекта, чем значение `String` второго объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если значение *str1* меньше значения *str2;* в противном случае, **ложные**.

## <a name="stringstring-constructor"></a><a name="ctor"></a>Строка::Струнный конструктор

Инициализирует новый экземпляр `String` класса с копией данных строки ввода.

### <a name="syntax"></a>Синтаксис

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>Параметры

*s*<br/>
Серия расширенных символов, инициализирующих строку.  char16

*n*<br/>
Число, указывающее длину строки.

### <a name="remarks"></a>Remarks

Если производительность имеет решающее значение и вы контролируете срок службы строки исходного кода, вы можете использовать [Платформу::StringReference](../cppcx/platform-stringreference-class.md) вместо строки.

### <a name="example"></a>Пример

```cpp
String^ s = L"Hello!";
```

## <a name="stringtostring"></a><a name="tostring"></a>Строка::ToString

Возвращает `String` объект, значение которого совпадает с текущей строкой.

### <a name="syntax"></a>Синтаксис

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `String` значение которого совпадает с текущей строкой.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
