---
title: Функции &lt;iomanip&gt;
ms.date: 11/04/2016
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
helpviewer_keywords:
- std::get_money [C++]
- std::get_time [C++]
- std::put_money [C++]
- std::put_time [C++]
- std::quoted [C++]
- std::resetiosflags [C++]
- std::setbase [C++]
- std::setfill [C++]
- std::setiosflags [C++]
- std::setprecision [C++]
- std::setw [C++]
ms.openlocfilehash: 0ed59a94c6b1c7d962b566e2a6b186ffb617a26a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375428"
---
# <a name="ltiomanipgt-functions"></a>Функции &lt;iomanip&gt;

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[Цитирует](#quoted)|[resetiosflags](#resetiosflags)|
|[установленная база](#setbase)|[сет-филл](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="get_money"></a><a name="iomanip_get_money"></a>get_money

Извлекает из потока денежное значение, используя нужный формат, и возвращает значение в параметре.

```cpp
template <class Money>
T7 get_money(Money& amount, bool use_intl);
```

### <a name="parameters"></a>Параметры

*Сумма*\
Извлеченное денежное значение.

*use_intl*\
Если **это правда,** используйте международный формат. По умолчанию используется значение **false**.

### <a name="remarks"></a>Remarks

Манипулятор возвращает объект, который при `str`извлечении из `formatted input function` потока ведет `get` себя как функция, `money_get` которая `str`вызывает функцию элемента для грани локаль, связанной с, используя *use_intl* для обозначения международного формата. В случае успеха, вызов хранит в *размере* извлеченной денежной стоимости. Затем манипулятор возвращает `str`.

`Money` должен иметь тип `long double` или быть экземпляром `basic_string` с теми же параметрами элемента и признаков, что и `str`.

## <a name="get_time"></a><a name="iomanip_get_time"></a>get_time

Извлекает значение времени из потока, используя нужный формат. Возвращает значение в параметре в виде структуры времени.

```cpp
template <class Elem>
T10 put_time(struct tm *time_ptr, const Elem *time_format);
```

### <a name="parameters"></a>Параметры

*time_ptr*\
Время в виде структуры времени.

*time_format*\
Требуемый формат для получения значения времени.

### <a name="remarks"></a>Remarks

Манипулятор возвращает объект, который при извлечении из потока `str` ведет себя как `formatted input function`, вызывающий функцию-член `get` для ограничения языкового стандарта `time_get`, связанного с `str`, с использованием `tptr` для указания структуры времени и `fmt` для указания начала строки формата, завершающейся нулем. В случае успешного выполнения вызов хранит в структуре времени значения, связанные с полями извлеченного времени. Затем манипулятор возвращает `str`.

## <a name="put_money"></a><a name="iomanip_put_money"></a>put_money

Вставляет денежную сумму в поток, используя нужный формат.

```cpp
template <class Money>
T8 put_money(const Money& amount, bool use_intl);
```

### <a name="parameters"></a>Параметры

*Сумма*\
Денежная сумма для вставки в поток.

*use_intl*\
Установить **на верно,** если манипулятор должен использовать международный формат, **ложные,** если он не должен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `str`.

### <a name="remarks"></a>Remarks

Манипулятор возвращает объект, который при вставке в поток `str` ведет себя как форматированная выходная функция, вызывающая функцию-член `put` для ограничения языкового стандарта `money_put`, связанного с `str`. В случае успеха вызов `amount` вставляется соответствующим образом отформатированным, используя *use_intl* для обозначения международного формата и, `str.fill()`как элемент заполнения. Затем манипулятор возвращает `str`.

`Money` должен иметь тип `long double` или быть экземпляром `basic_string` с теми же параметрами элемента и признаков, что и `str`.

## <a name="put_time"></a><a name="iomanip_put_time"></a>put_time

Записывает значение времени из структуры времени в поток с использованием указанного формата.

```cpp
template <class Elem>
T10 put_time(struct tm* time_ptr, const Elem* time_format);
```

### <a name="parameters"></a>Параметры

*time_ptr*\
Значение времени для записи в поток в виде структуры времени.

*time_format*\
Требуемый формат для записи значения времени.

### <a name="remarks"></a>Remarks

Манипулятор возвращает объект, который при вставке в поток `str` ведет себя как `formatted output function`. Функция вывода вызывает функцию-член `put` для ограничения языкового стандарта `time_put`, связанного с `str`. Функция вывода использует *time_ptr* для обозначения структуры времени и *time_format* для обозначения начала строки формата с нулевым завершением. В случае успешного выполнения вызов вставляет текст из строки формата и преобразованные значения из структуры времени. Затем манипулятор возвращает `str`.

## <a name="quoted"></a><a name="quoted"></a>Цитирует

**(Новое в C++14)** Манипулятор iostream, который обеспечивает удобное обращение строк в потоки и из них с помощью операторов >> и <<.

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>Параметры

*Ул*\
Std::string, char,\*строка буквальная или сырая строка буквально, или широкая версия любого из\*них (например, std::wstring, wchar_t).

*Разделитель*\
Указанный пользователем символ или двухбайтовый символ для использования в качестве разделителя для начала и конца строки.

*Побег*\
Указанный пользователем символ или двухбайтовый символ для использования в качестве escape-символа для escape-последовательностей в строке.

### <a name="remarks"></a>Remarks

См. раздел [Использование операторов вставки и управление форматом](../standard-library/using-insertion-operators-and-controlling-format.md).

### <a name="example"></a>Пример

В этом примере показано, как использовать `quoted` с разделителем по умолчанию и escape-символ с помощью узких строк. Широкие строки также поддерживаются.

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_quoted_v_nonquoted()
{
    // Results are identical regardless of input string type:
    // string inserted { R"(This is a "sentence".)" }; // raw string literal
    // string inserted { "This is a \"sentence\"." };  // regular string literal
    const char* inserted = "This is a \"sentence\".";  // const char*
    stringstream ss, ss_quoted;
    string extracted, extracted_quoted;

    ss << inserted;
    ss_quoted << quoted(inserted);

    cout << "ss.str() is storing       : " << ss.str() << endl;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;

    // Round-trip the strings
    ss >> extracted;
    ss_quoted >> quoted(extracted_quoted);

    cout << "After round trip: " << endl;
    cout << "Non-quoted      : " << extracted << endl;
    cout << "Quoted          : " << extracted_quoted << endl;
}

int main(int argc, char* argv[])
{
    show_quoted_v_nonquoted();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}

/* Output:
ss.str() is storing       : This is a "sentence".
ss_quoted.str() is storing: "This is a \"sentence\"."

After round trip:
Non-quoted      : This
Quoted          : This is a "sentence".

Press Enter to exit
*/
```

### <a name="example"></a>Пример

В следующем примере демонстрируется, как указать пользовательский разделитель или escape-символ:

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_custom_delimiter()
{
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    stringstream ss, ss_quoted;
    string extracted;

    ss_quoted << quoted(inserted, '*');
    ss << inserted;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;

    // Use the same quoted arguments as on insertion.
    ss_quoted >> quoted(extracted, '*');

    cout << "After round trip: " << endl;
    cout << "Quoted          : " << extracted << endl;

    extracted = {};
    ss >> extracted;
    cout << "Non-quoted      : " << extracted << endl << endl;
}

void show_custom_escape()
{
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };
    stringstream ss, ss_quoted, ss_quoted_custom;
    string extracted;

    // Use '"' as delimiter and '~' as escape character.
    ss_quoted_custom << quoted(inserted, '"', '~');
    ss_quoted << quoted(inserted);
    ss << inserted;
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;
    cout << "ss.str()              : " << ss.str() << endl << endl;

    // No spaces in this string, so non-quoted behaves same as quoted
    // after round-tripping.
}

int main(int argc, char* argv[])
{
    cout << "Custom delimiter:" << endl;
    show_custom_delimiter();
    cout << "Custom escape character:" << endl;
    show_custom_escape();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}
/* Output:
Custom delimiter:
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".

After round trip:
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".
Non-quoted      : "This"

Custom escape character:
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"
ss.str()              : \\root\trunk\branch\nest\egg\yolk

Press Enter to exit
*/
```

## <a name="resetiosflags"></a><a name="resetiosflags"></a>сбросить флаги

Удаляет указанные флаги.

```cpp
T1 resetiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>Параметры

*Маска*\
Флажки, которые нужно очистить.

### <a name="return-value"></a>Возвращаемое значение

Манипулятор возвращает объект, который, при извлечении или вставленном в потоке, `str`вызывает `str.` [набор](../standard-library/ios-base-class.md#setf)`(ios_base::`[fmtflags,](../standard-library/ios-base-class.md#fmtflags)`, mask)`а затем возвращается. `str`

### <a name="example"></a>Пример

См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `resetiosflags`.

## <a name="setbase"></a><a name="setbase"></a>установленная база

Задает основание целых чисел.

```cpp
T3 setbase(int base);
```

### <a name="parameters"></a>Параметры

*Базы*\
Основание числа.

### <a name="return-value"></a>Возвращаемое значение

Манипулятор возвращает объект, который, когда извлеченизирован из или вставлен в поток, `str`вызывает `str.setf(mask,` [ios_base::basefield](../standard-library/ios-base-class.md#fmtflags)`)`, а затем возвращается. `str` Здесь `mask` определяется следующим образом:

- Если *база* 8, `mask` `ios_base::`то [окт.](../standard-library/ios-functions.md#oct)

- Если *база* 10, то `ios_base::`маска [dec](../standard-library/ios-functions.md#dec).

- Если *база* 16, `mask` `ios_base::`то [hex](../standard-library/ios-functions.md#hex).

- Если *основание* любое другое `ios_base::`значение, то маска [fmtflags](../standard-library/ios-base-class.md#fmtflags)`(0)`.

### <a name="example"></a>Пример

См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setbase`.

## <a name="setfill"></a><a name="setfill"></a>сет-филл

Задает символ, который будет использоваться для заполнения пробелов на экране с выравниванием по правому краю.

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>Параметры

*Ch*\
Задает символ, который будет использоваться для заполнения пробелов при показе с выравниванием по правому краю.

### <a name="return-value"></a>Возвращаемое значение

Манипулятор шаблона возвращает объект, который, когда `str`извлечен `str.`из или вставлен в поток, вызовы [заполняют,](../standard-library/basic-ios-class.md#fill)`(Ch)`а затем возвращает. `str` Тип `Elem` должен быть таким же, как `str`тип элемента для потока.

### <a name="example"></a>Пример

См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setfill`.

## <a name="setiosflags"></a><a name="setiosflags"></a>setiosфлаги

Задает указанные флаги.

```cpp
T2 setiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>Параметры

*Маска*\
Флажки, которые нужно установить.

### <a name="return-value"></a>Возвращаемое значение

Манипулятор возвращает объект, который, когда извлечены `str`из `str.`или вставлены `str`в поток , вызовы [setf](../standard-library/ios-base-class.md#setf)`(mask)`, а затем возвращается.

### <a name="example"></a>Пример

См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setiosflags`.

## <a name="setprecision"></a><a name="setprecision"></a>setprecision

Задает точность для значений с плавающей запятой.

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>Параметры

*Прек*\
Точность для значений с плавающей запятой.

### <a name="return-value"></a>Возвращаемое значение

Манипулятор возвращает объект, который, когда извлечены `str`из `str.`или вставлены в поток , вызывает [точность](../standard-library/ios-base-class.md#precision)`(Prec)`, а затем возвращается. `str`

### <a name="example"></a>Пример

См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setprecision`.

## <a name="setw"></a><a name="setw"></a>Setw

Ширина поля отображения для следующего элемента в потоке.

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>Параметры

*Широкий*\
Ширина поля отображения.

### <a name="return-value"></a>Возвращаемое значение

Манипулятор возвращает объект, который, при извлечении `str` `str.`или вставленном в поток, вызывает [ширину,](../standard-library/ios-base-class.md#width)`(Wide)`затем возвращается. `str`

### <a name="remarks"></a>Remarks

Setw задает ширину только для следующего элемента в потоке и должен вставляться перед каждым элементом, ширину которого нужно задать.

### <a name="example"></a>Пример

```cpp
// iomanip_setw.cpp
// compile with: /EHsc
// Defines the entry point for the console application.
//
// Sample use of the following manipulators:
//   resetiosflags
//   setiosflags
//   setbase
//   setfill
//   setprecision
//   setw

#include <iostream>
#include <iomanip>

using namespace std;

const double   d1 = 1.23456789;
const double   d2 = 12.3456789;
const double   d3 = 123.456789;
const double   d4 = 1234.56789;
const double   d5 = 12345.6789;
const long      l1 = 16;
const long      l2 = 256;
const long      l3 = 1024;
const long      l4 = 4096;
const long      l5 = 65536;
int         base = 10;

void DisplayDefault( )
{
   cout << endl << "default display" << endl;
   cout << "d1 = " << d1 << endl;
   cout << "d2 = " << d2 << endl;
   cout << "d3 = " << d3 << endl;
   cout << "d4 = " << d4 << endl;
   cout << "d5 = " << d5 << endl;
}

void DisplayWidth( int n )
{
   cout << endl << "fixed width display set to " << n << ".\n";
   cout << "d1 = " << setw(n) << d1 << endl;
   cout << "d2 = " << setw(n) << d2 << endl;
   cout << "d3 = " << setw(n) << d3 << endl;
   cout << "d4 = " << setw(n) << d4 << endl;
   cout << "d5 = " << setw(n) << d5 << endl;
}

void DisplayLongs( )
{
   cout << setbase(10);
   cout << endl << "setbase(" << base << ")" << endl;
   cout << setbase(base);
   cout << "l1 = " << l1 << endl;
   cout << "l2 = " << l2 << endl;
   cout << "l3 = " << l3 << endl;
   cout << "l4 = " << l4 << endl;
   cout << "l5 = " << l5 << endl;
}

int main( int argc, char* argv[] )
{
   DisplayDefault( );

   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);
   DisplayDefault( );

   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);
   DisplayDefault( );

   cout << setiosflags(ios_base::scientific);
   cout << endl << "setiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << resetiosflags(ios_base::scientific);
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << endl << "setfill('" << 'S' << "')" << setfill('S');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);
   DisplayWidth(10);
   DisplayDefault( );

   base = 16;
   DisplayLongs( );

   base = 8;
   DisplayLongs( );

   base = 10;
   DisplayLongs( );

   return   0;
}
```

```Output

default display
d1 = 1.23457
d2 = 12.3457
d3 = 123.457
d4 = 1234.57
d5 = 12345.7

setprecision(3)
default display
d1 = 1.23
d2 = 12.3
d3 = 123
d4 = 1.23e+003
d5 = 1.23e+004

setprecision(12)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setiosflags(4096)
default display
d1 = 1.234567890000e+000
d2 = 1.234567890000e+001
d3 = 1.234567890000e+002
d4 = 1.234567890000e+003
d5 = 1.234567890000e+004

resetiosflags(4096)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill('S')
fixed width display set to 15.
d1 = SSSSS1.23456789
d2 = SSSSS12.3456789
d3 = SSSSS123.456789
d4 = SSSSS1234.56789
d5 = SSSSS12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill(' ')
fixed width display set to 15.
d1 =      1.23456789
d2 =      12.3456789
d3 =      123.456789
d4 =      1234.56789
d5 =      12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setprecision(8)
fixed width display set to 10.
d1 =  1.2345679
d2 =  12.345679
d3 =  123.45679
d4 =  1234.5679
d5 =  12345.679

default display
d1 = 1.2345679
d2 = 12.345679
d3 = 123.45679
d4 = 1234.5679
d5 = 12345.679

setbase(16)
l1 = 10
l2 = 100
l3 = 400
l4 = 1000
l5 = 10000

setbase(8)
l1 = 20
l2 = 400
l3 = 2000
l4 = 10000
l5 = 200000

setbase(10)
l1 = 16
l2 = 256
l3 = 1024
l4 = 4096
l5 = 65536
```

## <a name="see-also"></a>См. также раздел

[\<iomanip>](../standard-library/iomanip.md)
