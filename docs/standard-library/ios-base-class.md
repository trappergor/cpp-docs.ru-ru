---
title: Класс ios_base | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xiosbase/std::ios_base
- ios/std::ios_base::event_callback
- xiosbase/std::ios_base::fmtflags
- xiosbase/std::ios_base::iostate
- xiosbase/std::ios_base::openmode
- xiosbase/std::ios_base::seekdir
- xiosbase/std::ios_base::event
- xiosbase/std::ios_base::adjustfield
- xiosbase/std::ios_base::app
- xiosbase/std::ios_base::ate
- xiosbase/std::ios_base::badbit
- xiosbase/std::ios_base::basefield
- xiosbase/std::ios_base::beg
- xiosbase/std::ios_base::binary
- xiosbase/std::ios_base::boolalpha
- xiosbase/std::ios_base::cur
- xiosbase/std::ios_base::dec
- xiosbase/std::ios_base::end
- xiosbase/std::ios_base::eofbit
- xiosbase/std::ios_base::failbit
- xiosbase/std::ios_base::fixed
- xiosbase/std::ios_base::floatfield
- xiosbase/std::ios_base::goodbit
- xiosbase/std::ios_base::hex
- xiosbase/std::ios_base::in
- xiosbase/std::ios_base::internal
- xiosbase/std::ios_base::left
- xiosbase/std::ios_base::oct
- xiosbase/std::ios_base::out
- xiosbase/std::ios_base::right
- xiosbase/std::ios_base::scientific
- xiosbase/std::ios_base::showbase
- xiosbase/std::ios_base::showpoint
- xiosbase/std::ios_base::showpos
- xiosbase/std::ios_base::skipws
- xiosbase/std::ios_base::trunc
- xiosbase/std::ios_base::unitbuf
- xiosbase/std::ios_base::uppercase
- xiosbase/std::ios_base::failure
- xiosbase/std::ios_base::flags
- xiosbase/std::ios_base::getloc
- xiosbase/std::ios_base::imbue
- xiosbase/std::ios_base::Init
- xiosbase/std::ios_base::iword
- xiosbase/std::ios_base::precision
- xiosbase/std::ios_base::pword
- ios/std::ios_base::register_callback
- xiosbase/std::ios_base::setf
- xiosbase/std::ios_base::sync_with_stdio
- xiosbase/std::ios_base::unsetf
- xiosbase/std::ios_base::width
- xiosbase/std::ios_base::xalloc
dev_langs:
- C++
helpviewer_keywords:
- std::ios_base [C++]
- std::ios_base [C++], event_callback
- std::ios_base [C++], fmtflags
- std::ios_base [C++], iostate
- std::ios_base [C++], openmode
- std::ios_base [C++], seekdir
- std::ios_base [C++], event
- std::ios_base [C++], adjustfield
- std::ios_base [C++], app
- std::ios_base [C++], ate
- std::ios_base [C++], badbit
- std::ios_base [C++], basefield
- std::ios_base [C++], beg
- std::ios_base [C++], binary
- std::ios_base [C++], boolalpha
- std::ios_base [C++], cur
- std::ios_base [C++], dec
- std::ios_base [C++], end
- std::ios_base [C++], eofbit
- std::ios_base [C++], failbit
- std::ios_base [C++], fixed
- std::ios_base [C++], floatfield
- std::ios_base [C++], goodbit
- std::ios_base [C++], hex
- std::ios_base [C++], in
- std::ios_base [C++], internal
- std::ios_base [C++], left
- std::ios_base [C++], oct
- std::ios_base [C++], out
- std::ios_base [C++], right
- std::ios_base [C++], scientific
- std::ios_base [C++], showbase
- std::ios_base [C++], showpoint
- std::ios_base [C++], showpos
- std::ios_base [C++], skipws
- std::ios_base [C++], trunc
- std::ios_base [C++], unitbuf
- std::ios_base [C++], uppercase
- std::ios_base [C++], failure
- std::ios_base [C++], flags
- std::ios_base [C++], getloc
- std::ios_base [C++], imbue
- std::ios_base [C++], Init
- std::ios_base [C++], iword
- std::ios_base [C++], precision
- std::ios_base [C++], pword
- std::ios_base [C++], register_callback
- std::ios_base [C++], setf
- std::ios_base [C++], sync_with_stdio
- std::ios_base [C++], unsetf
- std::ios_base [C++], width
- std::ios_base [C++], xalloc
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 818d6fad62ec4d506215a82f2faa1e3aa58d1654
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="iosbase-class"></a>Класс ios_base

Этот класс описывает хранилище и функции-члены общие для обоих потоков (ввода и вывода), не зависящих от параметров шаблона. (Класс шаблона [basic_ios](../standard-library/basic-ios-class.md) описывает общие принципы и зависит от параметров шаблона.)

Объект класса ios_base хранит сведения о форматировании, состоящие из следующих элементов:

- Флаги форматирования в объекте типа [fmtflags](#fmtflags).

- Маска исключения в объекте типа [iostate](#iostate).

- Ширина поля в тип объекта `int`.

- Точность отображения в объекте типа `int`.

- Объект языкового стандарта в объекте типа **locale**.

- Два расширяемых массива с элементами типа **long** и указателем `void`.

Объект класса ios_base также хранит сведения о состоянии потока в объекте типа [iostate](#iostate) и стеке обратных вызовов.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[ios_base](#ios_base)|Создает объект `ios_base`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[event_callback](#event_callback)|Описывает функцию, передаваемую в [register_call](#register_callback).|
|[fmtflags](#fmtflags)|Константы для определения внешнего вида выходных данных.|
|[iostate](#iostate)|Определяет константы, описывающие состояние потока.|
|[openmode](#openmode)|Описывает процесс взаимодействия с потоком.|
|[seekdir](#seekdir)|Задает начальную точку для операций смещения.|

### <a name="enums"></a>Перечисления

|||
|-|-|
|[event](#event)|Задает типы событий.|

### <a name="constants"></a>Константы

|||
|-|-|
|[adjustfield](#fmtflags)|Битовая маска, определенная как `internal` &#124; `left` &#124; `right`.|
|[app](#openmode)|Задает поиск до конца потока перед каждой вставкой.|
|[ate](#openmode)|Задает поиск до конца потока при первом создании его управляющего объекта.|
|[badbit](#iostate)|Регистрирует потерю целостности буфера потока.|
|[basefield](#fmtflags)|Битовая маска, определенная как `dec` &#124; `hex` &#124; `oct`.|
|[beg](#seekdir)|Задает поиск относительно начала последовательности.|
|[binary](#openmode)|Указывает, что файл должен быть считан как двоичный, а не текстовый поток.|
|[boolalpha](#fmtflags)|Задает вставку или извлечение объектов типа `bool` в качестве имен (таких как `true` и `false`), а не числовых значений.|
|[cur](#seekdir)|Задает поиск относительно текущей позиции в последовательности.|
|[dec](#fmtflags)|Задает вставку или извлечение целочисленных значений в десятичном формате.|
|[end](#seekdir)|Задает поиск относительно конца последовательности.|
|[eofbit](#iostate)|Регистрирует конец файла при извлечении из потока.|
|[failbit](#iostate)|Регистрирует сбой при извлечении допустимого поля из потока.|
|[fixed](#fmtflags)|Задает вставку значений с плавающей запятой в формате с фиксированной запятой (без поля экспоненты).|
|[floatfield](#fmtflags)|Битовая маска, определенная как `fixed` &#124; `scientific`|
|[goodbit](#iostate)|Очищает все биты состояния.|
|[hex](#fmtflags)|Задает вставку или извлечение целочисленных значений в шестнадцатеричном формате.|
|[in](#openmode)|Задает извлечение из потока.|
|[internal](#fmtflags)|Выполняет заполнение по ширине поля, вставляя символы заполнения в точке внутри созданного числового поля.|
|[left](#fmtflags)|Задает выравнивание по левому краю.|
|[oct](#fmtflags)|Задает вставку или извлечение целочисленных значений в восьмеричном формате.|
|[out](#openmode)|Задает вставку в поток.|
|[right](#fmtflags)|Задает выравнивание по правому краю.|
|[scientific](#fmtflags)|Задает вставку значений с плавающей запятой в экспоненциальном формате (с полем экспоненты).|
|[showbase](#fmtflags)|Задает вставку префикса, отображающего базу созданного целочисленного поля.|
|[showpoint](#fmtflags)|Задает безусловную вставку десятичной запятой в созданное поле с плавающей запятой.|
|[showpos](#fmtflags)|Задает вставку знака плюс в созданное неотрицательное числовое поле.|
|[skipws](#fmtflags)|Задает пропуск начальных пробелов перед определенными извлечениями.|
|[trunc](#openmode)|Задает удаление содержимого существующего файла при создании его управляющего объекта.|
|[unitbuf](#fmtflags)|Обеспечивает запись выходных данных на диск после каждой вставки.|
|[uppercase](#fmtflags)|Задает вставку эквивалентных прописных букв для букв нижнего регистра в определенных вставках.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[failure](#failure)|Класс-член служит базовым классом для всех исключений, выдаваемых функцией-членом [clear](../standard-library/basic-ios-class.md#clear) в классе шаблона [basic_ios](../standard-library/basic-ios-class.md).|
|[flags](#flags)|Задает или возвращает текущие параметры флага.|
|[getloc](#getloc)|Возвращает сохраненный объект языкового стандарта.|
|[imbue](#imbue)|Изменяет языковой стандарт.|
|[Init](#init)|Создает стандартные объекты iostream при построении.|
|[iword](#iword)|Присваивает значение, сохраняемое в виде `iword`.|
|[precision](#precision)|Задает количество цифр для отображения числа с плавающей запятой.|
|[pword](#pword)|Присваивает значение, сохраняемое в виде `pword`.|
|[register_callback](#register_callback)|Задает функцию обратного вызова.|
|[setf](#setf)|Задает указанные флаги.|
|[sync_with_stdio](#sync_with_stdio)|Гарантирует, что операции с iostream и библиотекой времени выполнения C выполняются в том порядке, в котором они расположены в исходном коде.|
|[unsetf](#unsetf)|Отключает указанные флаги.|
|[width](#width)|Задает длину потока вывода.|
|[xalloc](#xalloc)|Указывает, что переменная должна быть частью потока.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Оператор присваивания для объектов `ios_base`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<ios>

**Пространство имен:** std

## <a name="event"></a>  ios_base::event

Задает типы событий.

```cpp
enum event {
    erase_event,
    imbue_event,
    copyfmt_event};
```

### <a name="remarks"></a>Примечания

Тип — перечисляемый тип, описывающий объект, который может хранить событие обратного вызова, использованное в качестве аргумента для функции, зарегистрированной в [register_callback](#register_callback). Различные значения события:

- **copyfmt_event**, чтобы определить обратный вызов, который происходит в конце вызова [copyfmt](../standard-library/basic-ios-class.md#copyfmt), непосредственно перед копированием [маски исключения](../standard-library/ios-base-class.md).

- **erase_event**, чтобы определить обратный вызов, который происходит в начале вызова [copyfmt](../standard-library/basic-ios-class.md#copyfmt) или в начале вызова деструктора для  **\*this**.

- **imbue_event**, чтобы определить обратный вызов, который происходит в конце вызова [imbue](#imbue), сразу перед возвратом из функции.

### <a name="example"></a>Пример

Для примера см. [register_callback](#register_callback).

## <a name="event_callback"></a>  ios_base::event_callback

Описывает функцию, передаваемую в [register_call](#register_callback).

```cpp
typedef void (__cdecl *event_callback)(
    event _E,
    ios_base& _Base,
    int _I);
```

### <a name="parameters"></a>Параметры

*_E* [событие](#event).

`_Base` Поток, в котором событие было вызвано.

*Я* несколько определяемых пользователем.

### <a name="remarks"></a>Примечания

Тип описывает указатель на функцию, которая может быть зарегистрирована с помощью [register_callback](#register_callback). Функции этого типа не должны вызывать исключение.

### <a name="example"></a>Пример

См. [register_call](#register_callback) для примера с использованием `event_callback`.

## <a name="failure"></a>  ios_base::failure

Класс `failure` определяет базовый класс для типов всех объектов, вызываемых как исключения, с помощью функций в библиотеке `iostreams`, для отчетов об ошибках, обнаруженных во время операций буфера потока.

```cpp
namespace std {
    class failure : public system_error {
    public:
        explicit failure(
            const string& _Message,
            const error_code& _Code = io_errc::stream);

        explicit failure(
            const char* str,
            const error_code& _Code = io_errc::stream);
    };
}
```

### <a name="remarks"></a>Примечания

Значение, возвращаемое `what()`, — это копия `_Message`, возможно, дополненная тестом на основе `_Code`. Если значение `_Code` не указано, значение по умолчанию — `make_error_code(io_errc::stream)`.

### <a name="example"></a>Пример

```cpp
// ios_base_failure.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.exceptions(ios::failbit);
    try
    {
        file.open( "rm.txt", ios_base::in );
        // Opens nonexistent file for reading
    }
    catch( ios_base::failure f )
    {
        cout << "Caught an exception: " << f.what() << endl;
    }
}
```

```Output
Caught an exception: ios_base::failbit set
```

## <a name="flags"></a>  ios_base::flags

Задает или возвращает текущие параметры флага.

```cpp
fmtflags flags() const;
fmtflags flags(fmtflags fmtfl);
```

### <a name="parameters"></a>Параметры

`fmtfl` Новый `fmtflags` параметр.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее или текущее значение `fmtflags`.

### <a name="remarks"></a>Примечания

Список флагов см. в разделе [ios_base::fmtflags](#fmtflags).

Первая функция-член возвращает сохраненные флажки формата. Вторая функция-член сохраняет `fmtfl` во флажках формата и возвращает свое ранее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// ios_base_flags.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    cout << cout.flags( ) << endl;
    cout.flags( ios::dec | ios::boolalpha );
    cout << cout.flags( );
}
```

```Output
513
16896
```

## <a name="fmtflags"></a>  ios_base::fmtflags

Константы для определения внешнего вида выходных данных.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type fmtflags;
   static const fmtflags boolalpha;
   static const fmtflags dec;
   static const fmtflags fixed;
   static const fmtflags hex;
   static const fmtflags internal;
   static const fmtflags left;
   static const fmtflags oct;
   static const fmtflags right;
   static const fmtflags scientific;
   static const fmtflags showbase;
   static const fmtflags showpoint;
   static const fmtflags showpos;
   static const fmtflags skipws;
   static const fmtflags unitbuf;
   static const fmtflags uppercase;
   static const fmtflags adjustfield;
   static const fmtflags basefield;
   static const fmtflags floatfield;
   // ...
};
```

### <a name="remarks"></a>Примечания

Поддерживает манипуляторы в [ios](../standard-library/ios.md).

Тип — это тип битовой маски, описывающий объект, который может хранить флаги формата. Ниже перечислены значения различных флагов (элементы).

- `dec`, чтобы вставить или извлечь целочисленные значения в десятичном формате.

- `hex`, чтобы вставить или извлечь целочисленные значения в шестнадцатеричном формате.

- `oct`, чтобы вставить или извлечь целочисленные значения в восьмеричном формате.

- `showbase`, чтобы вставить префикс, отображающий базу созданного целочисленного поля.

- `internal`, чтобы выполнить заполнение по ширине поля, вставляя символы заполнения в точке внутри созданного числового поля. (Сведения об установке ширины поля см. в разделе [setw](../standard-library/iomanip-functions.md#setw).)

- `left`, чтобы выполнить заполнение по ширине поля, вставляя символы заполнения в конец созданного числового поля (выравнивание по левому краю).

- `right`, чтобы выполнить заполнение по ширине поля, вставляя символы заполнения в начало созданного числового поля (выравнивание по правому краю).

- `boolalpha`, чтобы вставить или извлечь объекты типа `bool`, например имена (такие как `true` и `false`), а не числовые значения.

- `fixed`, чтобы вставить значения с плавающей запятой в формате с фиксированной запятой (без поля экспоненты).

- `scientific`, чтобы вставить значения с плавающей запятой в экспоненциальном формате (с полем экспоненты).

- `showpoint`, чтобы выполнить безусловную вставку десятичной запятой в созданное поле с плавающей запятой.

- `showpos`, чтобы вставить знак плюс в созданное неотрицательное числовое поле.

- `skipws`, чтобы пропустить начальные пробелы перед определенными извлечениями.

- `unitbuf`, чтобы записывать выходные данные на диск после каждой вставки.

- `uppercase`, чтобы вставить эквивалентные прописные буквы для букв нижнего регистра в определенных вставках.

Кроме того, ниже приведено несколько полезных значений:

- `adjustfield`, битовая маска, определенная как `internal` &#124; `left` &#124; `right`

- `basefield`, определенная как `dec` &#124; `hex` &#124; `oct`

- `floatfield`, определенная как `fixed` &#124; `scientific`

Примеры функций, которые изменяют эти флажки формата, см. в разделе [\<iomanip>](../standard-library/iomanip.md).

## <a name="getloc"></a>  ios_base::getloc

Возвращает сохраненный объект языкового стандарта.

```cpp
locale getloc() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект языкового стандарта.

### <a name="example"></a>Пример

```cpp
// ios_base_getlock.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << cout.getloc( ).name( ).c_str( ) << endl;
}
```

```Output
C
```

## <a name="imbue"></a>  ios_base::imbue

Изменяет языковой стандарт.

```cpp
locale imbue(const locale& _Loc);
```

### <a name="parameters"></a>Параметры

`_Loc` Новый параметр языкового стандарта.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий языковой стандарт.

### <a name="remarks"></a>Примечания

Функция-член сохраняет `_Loc` в объект языкового стандарта, а затем сообщает событие обратного вызова и `imbue_event`. Она возвращает предыдущее сохраненное значение.

### <a name="example"></a>Пример

Пример см. в разделе [basic_ios::imbue](../standard-library/basic-ios-class.md#imbue).

## <a name="init"></a>  ios_base::Init

Создает стандартные объекты iostream при построении.

```cpp
class Init { };
```

### <a name="remarks"></a>Примечания

Вложенный класс описывает объект, конструкция которого гарантирует, что стандартные объекты iostreams создаются должным образом, еще до выполнения конструктора произвольного статического объекта.

## <a name="ios_base"></a>  ios_base::ios_base

Создает объекты ios_base.

```cpp
ios_base();
```

### <a name="remarks"></a>Примечания

(Защищенный) конструктор ничего не делает. Последующий вызов **basic_ios::**[init](../standard-library/basic-ios-class.md#init) должен инициализировать объект для возможности его безопасного уничтожения. Таким образом, единственным безопасным использованием класса ios_base является базовый класс для класса шаблона [basic_ios](../standard-library/basic-ios-class.md).

## <a name="iostate"></a>  ios_base::iostate

Тип констант, описывающих состояние потока.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Примечания

Тип — это тип битовой маски, описывающий объект, который может хранить данные о состоянии потока. Ниже перечислены значения различных флагов (элементы).

- `badbit` регистрирует потерю целостности буфера потока.

- `eofbit` регистрирует конец файла при извлечении из потока.

- `failbit` регистрирует ошибку извлечения корректного поля из потока.

Кроме того, полезным является значение `goodbit`, где не устанавливаются никакие из упомянутых ранее бит ( `goodbit` гарантированно ноль).

## <a name="iword"></a>  ios_base::iword

Присваивает значение, сохраняемое в виде `iword`.

```cpp
long& iword(int idx);
```

### <a name="parameters"></a>Параметры

`idx` Индекс значения, чтобы сохранить как `iword`.

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на элемент `idx` расширяемого массива с элементами типа **long**. Все элементы эффективно присутствуют и изначально хранят нулевое значение. Возвращаемая ссылка является недействительной после следующего вызова `iword` для объекта, после изменения объекта с помощью вызова **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) или после уничтожения объекта.

Если `idx` является отрицательным или уникальное хранилище недоступно для элемента, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** и возвращает ссылку, которая может не быть уникальной.

Чтобы получить уникальный индекс для использования со всеми объектами типа `ios_base`, вызовите [xalloc](#xalloc).

### <a name="example"></a>Пример

См. [xalloc](#xalloc) для примера использования `iword`.

## <a name="openmode"></a>  ios_base::openmode

Описывает процесс взаимодействия с потоком.

```cpp
class ios_base {
public:
   typedef implementation-defined-bitmask-type iostate;
   static const iostate badbit;
   static const iostate eofbit;
   static const iostate failbit;
   static const iostate goodbit;
   // ...
};
```

### <a name="remarks"></a>Примечания

Тип — `bitmask type`, описывающий объект, который может хранить режим открытия для нескольких объектов iostreams. Ниже перечислены значения различных флагов (элементы).

- **app** — поиск до конца потока перед каждой вставкой.

- **ate** — поиск до конца потока при первом создании его управляющего объекта.

- **binary** — читает файл как двоичный поток, а не как текстовый поток.

- **in** — разрешает извлечение из потока.

- **out** — разрешает вставку в поток.

- **trunc** — удаляет содержимое существующего файла при создании его управляющего объекта.

### <a name="example"></a>Пример

```cpp
// ios_base_openmode.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
}
```

## <a name="op_eq"></a>  ios_base::operator=

Оператор присваивания для объектов ios_base.

```cpp
ios_base& operator=(const ios_base& right);
```

### <a name="parameters"></a>Параметры

`right` Объект типа `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Объект, которому выполняется присваивание.

### <a name="remarks"></a>Примечания

Оператор копирует сохраненные сведения о форматировании, создавая новую копию для любых расширяемых массивов. Затем он возвращает **\*this**. Обратите внимание, что стек обратных вызовов не копируется.

Этот оператор используется только классами, производными от `ios_base`.

## <a name="precision"></a>  ios_base::precision

Задает количество цифр для отображения числа с плавающей запятой.

```cpp
streamsize precision() const;
streamsize precision(streamsize _Prec);
```

### <a name="parameters"></a>Параметры

`_Prec` Количество значащих цифр для отображения, или число цифр после десятичной запятой в нотации с фиксированной.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненное [количество цифр для отображения](../standard-library/ios-base-class.md). Вторая функция-член сохраняет `_Prec` в качестве количества цифр для отображения и возвращает свое ранее сохраненное значение.

### <a name="remarks"></a>Примечания

Числа с плавающей запятой отображаются в фиксированной нотации с помощью [fixed](../standard-library/ios-functions.md#fixed).

### <a name="example"></a>Пример

```cpp
// ios_base_precision.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    float i = 31.31234F;

    cout.precision( 3 );
    cout << i << endl;          // display three significant digits
    cout << fixed << i << endl; // display three digits after decimal
                                // point
}
```

```Output
31.3
31.312
```

## <a name="pword"></a>  ios_base::pword

Присваивает значение, сохраняемое в виде `pword`.

```cpp
void *& pword(int _Idx);
```

### <a name="parameters"></a>Параметры

`_Idx` Индекс значения, чтобы сохранить как `pword`.

### <a name="remarks"></a>Примечания

Функция-член возвращает ссылку на элемент _ *Idx* расширяемого массива с элементами типа указатель `void`. Все элементы эффективно присутствуют и изначально хранят нулевой указатель. Возвращаемая ссылка является недействительной после следующего вызова `pword` для объекта, после изменения объекта с помощью вызова **basic_ios::**[copyfmt](../standard-library/basic-ios-class.md#copyfmt) или после уничтожения объекта.

Если _ *Idx* является отрицательным или уникальное хранилище для элемента недоступно, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit)** и возвращает ссылку, которая может не быть уникальной.

Чтобы получить уникальный индекс для использования со всеми объектами типа `ios_base`, вызовите [xalloc](#xalloc).

### <a name="example"></a>Пример

См. [xalloc](#xalloc) с примером использования `pword`.

## <a name="register_callback"></a>  ios_base::register_callback

Задает функцию обратного вызова.

```cpp
void register_callback(
    event_callback pfn, int idx);
```

### <a name="parameters"></a>Параметры

`pfn` Указатель на функцию обратного вызова.

`idx` Определенный пользователем номер.

### <a name="remarks"></a>Примечания

Функция-член помещает пары `{pfn, idx}` стек хранимых обратного вызова [стек обратных вызовов](../standard-library/ios-base-class.md). При возникновении события обратного вызова **ev** сообщается, функции вызываются, в обратном порядке из реестра, с помощью выражения `(*pfn)(ev, *this, idx)`.

### <a name="example"></a>Пример

```cpp
// ios_base_register_callback.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

void callback1( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback1" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

void callback2( ios_base::event e, ios_base& stream, int arg )
{
    cout << "in callback2" << endl;
    switch ( e )
    {
    case ios_base::erase_event:
        cout << "an erase event" << endl;
        break;
    case ios_base::imbue_event:
        cout << "an imbue event" << endl;
        break;
    case ios_base::copyfmt_event:
        cout << "an copyfmt event" << endl;
        break;
    };
}

int main( )
{
    // Make sure the imbue will not throw an exception
    // assert( setlocale( LC_ALL, "german" )!=NULL );

    cout.register_callback( callback1, 0 );
    cin.register_callback( callback2, 0 );

    try
    {
        // If no exception because the locale's not found,
        // generate an imbue_event on callback1
        cout.imbue(locale("german"));
    }
    catch(...)
    {
        cout << "exception" << endl;
    }

    // This will
    // (1) erase_event on callback1
    // (2) copyfmt_event on callback2
    cout.copyfmt(cin);

    // We get two erase events from callback2 at the end because
    // both cin and cout have callback2 registered when cin and cout
    // are destroyed at the end of program.
}
```

```Output
in callback1
an imbue event
in callback1
an erase event
in callback2
an copyfmt event
in callback2
an erase event
in callback2
an erase event
```

## <a name="seekdir"></a> ios_base::seekdir

Задает начальную точку для операций смещения.

```cpp
namespace std {
    class ios_base {
    public:
        typedef implementation-defined-enumerated-type seekdir;
        static const seekdir beg;
        static const seekdir cur;
        static const seekdir end;
        // ...
    };
}
```

### <a name="remarks"></a>Примечания

Тип — перечислимый тип, описывающий объект, который может хранить режим поиска, используется в качестве аргумента для функции-члены классов, несколько потоков ввода-вывода. Ниже перечислены значения различных флагов.

- **beg** — поиск (изменение текущей позиции чтения или записи) по отношению к началу последовательности (массив, поток или файл).

- **cur** — поиск по отношению к текущей позиции в последовательности.

- **end** — поиск по отношению к концу последовательности.

### <a name="example"></a>Пример

```cpp
// ios_base_seekdir.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
    using namespace std;
    fstream file;
    file.open( "rm.txt", ios_base::out | ios_base::trunc );

    file << "testing";
    file.seekp( 0, ios_base::beg );
    file << "a";
    file.seekp( 0, ios_base::end );
    file << "a";
}
```

## <a name="setf"></a> ios_base::setf

Задает указанные флаги.

```cpp
fmtflags setf(
    fmtflags _Mask
);
fmtflags setf(
    fmtflags _Mask,
    fmtflags _Unset
);
```

### <a name="parameters"></a>Параметры

`_Mask` Флаги для включения.

*_Unset* флаги для отключения.

### <a name="return-value"></a>Возвращаемое значение

    The previous format flags

### <a name="remarks"></a>Примечания

    The first member function effectively calls [flags](#flags)(_ *Mask* &#124; \_ *Flags*) (set selected bits) and then returns the previous format flags. The second member function effectively calls **flags**(\_ *Mask* **& fmtfl, flags& ~**`_Mask`) (replace selected bits under a mask) and then returns the previous format flags.

### <a name="example"></a>Пример

```cpp
// ios_base_setf.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    int i = 10;
    cout << i << endl;

    cout.unsetf( ios_base::dec );
    cout.setf( ios_base::hex );
    cout << i << endl;

    cout.setf( ios_base::dec );
    cout << i << endl;
    cout.setf( ios_base::hex, ios_base::dec );
    cout << i << endl;
}
```

## <a name="sync_with_stdio"></a> ios_base::sync_with_stdio

Гарантирует, что операции с iostream и библиотекой времени выполнения C выполняются в том порядке, в котором они расположены в исходном коде.

```cpp
static bool sync_with_stdio(
   bool _Sync = true
);
```

### <a name="parameters"></a>Параметры

`_Sync` Являются ли все потоки в соответствии с **stdio**.

### <a name="return-value"></a>Возвращаемое значение

    Previous setting for this function.

### <a name="remarks"></a>Примечания

    The static member function stores a **stdio** sync flag, which is initially **true**. When **true**, this flag ensures that operations on the same file are properly synchronized between the [iostreams](../standard-library/iostreams-conventions.md) functions and those defined in the C++ Standard Library. Otherwise, synchronization may or may not be guaranteed, but performance may be improved. The function stores `_Sync` in the **stdio** sync flag and returns its previous stored value. You can call it reliably only before performing any operations on the standard streams.

## <a name="unsetf"></a> ios_base::unsetf

Отключает указанные флаги.

```cpp
void unsetf(
   fmtflags _Mask
);
```

### <a name="parameters"></a>Параметры

`_Mask` Флаги, которые требуется отключить.

### <a name="remarks"></a>Примечания

    The member function effectively calls [flags](#flags)(`~`*_Mask* **& flags**) (clear selected bits).

### <a name="example"></a>Пример

    See [ios_base::setf](#setf) for a sample of using `unsetf`.

## <a name="width"></a> ios_base::width

Задает длину потока вывода.

```cpp
streamsize width( ) const;
streamsize width(
   streamsize _Wide
);
```

### <a name="parameters"></a>Параметры

`_Wide` Требуемый размер выходного потока.

### <a name="return-value"></a>Возвращаемое значение

    The current width setting.

### <a name="remarks"></a>Примечания

    The first member function returns the stored field width. The second member function stores `_Wide` in the field width and returns its previous stored value.

### <a name="example"></a>Пример

```cpp
// ios_base_width.cpp
// compile with: /EHsc
#include <iostream>

int main( ) {
    using namespace std;

    cout.width( 20 );
    cout << cout.width( ) << endl;
    cout << cout.width( ) << endl;
}
```

```Output
20
0
```

## <a name="xalloc"></a> ios_base::xalloc

    Specifies that a variable is part of the stream.

```cpp
static int xalloc( );
```

### <a name="return-value"></a>Возвращаемое значение

    The static member function returns a stored static value, which it increments on each call.

### <a name="remarks"></a>Примечания

    You can use the return value as a unique index argument when calling the member functions [iword](#iword) or [pword](#pword).

### <a name="example"></a>Пример

```cpp
// ios_base_xalloc.cpp
// compile with: /EHsc
// Lets you store user-defined information.
// iword, jword, xalloc
#include <iostream>

int main( )
{
    using namespace std;

    static const int i = ios_base::xalloc();
    static const int j = ios_base::xalloc();
    cout.iword( i ) = 11;
    cin.iword( i ) = 13;
    cin.pword( j ) = "testing";
    cout << cout.iword( i ) << endl;
    cout << cin.iword( i ) << endl;
    cout << ( char * )cin.pword( j ) << endl;
}
```

```Output
11
13
testing
```

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
