---
title: Класс moneypunct
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct
- xlocmon/std::moneypunct::char_type
- xlocmon/std::moneypunct::string_type
- xlocmon/std::moneypunct::curr_symbol
- xlocmon/std::moneypunct::decimal_point
- xlocmon/std::moneypunct::do_curr_symbol
- xlocmon/std::moneypunct::do_decimal_point
- xlocmon/std::moneypunct::do_frac_digits
- xlocmon/std::moneypunct::do_grouping
- xlocmon/std::moneypunct::do_neg_format
- xlocmon/std::moneypunct::do_negative_sign
- xlocmon/std::moneypunct::do_pos_format
- xlocmon/std::moneypunct::do_positive_sign
- xlocmon/std::moneypunct::do_thousands_sep
- xlocmon/std::moneypunct::frac_digits
- xlocmon/std::moneypunct::grouping
- xlocmon/std::moneypunct::neg_format
- xlocmon/std::moneypunct::negative_sign
- xlocmon/std::moneypunct::pos_format
- xlocmon/std::moneypunct::positive_sign
- xlocmon/std::moneypunct::thousands_sep
helpviewer_keywords:
- std::moneypunct [C++]
- std::moneypunct [C++], char_type
- std::moneypunct [C++], string_type
- std::moneypunct [C++], curr_symbol
- std::moneypunct [C++], decimal_point
- std::moneypunct [C++], do_curr_symbol
- std::moneypunct [C++], do_decimal_point
- std::moneypunct [C++], do_frac_digits
- std::moneypunct [C++], do_grouping
- std::moneypunct [C++], do_neg_format
- std::moneypunct [C++], do_negative_sign
- std::moneypunct [C++], do_pos_format
- std::moneypunct [C++], do_positive_sign
- std::moneypunct [C++], do_thousands_sep
- std::moneypunct [C++], frac_digits
- std::moneypunct [C++], grouping
- std::moneypunct [C++], neg_format
- std::moneypunct [C++], negative_sign
- std::moneypunct [C++], pos_format
- std::moneypunct [C++], positive_sign
- std::moneypunct [C++], thousands_sep
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
ms.openlocfilehash: 750b61100f7e3fe15851fffbedeb5b60d4d7034f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349125"
---
# <a name="moneypunct-class"></a>Класс moneypunct

Класс шаблона описывает объект, который можно использовать в качестве аспекта языкового стандарта для описания последовательностей типа *CharType* используются для представления полей для ввода или вывода денежных значений. Если параметр шаблона *Intl* — *true*, соблюдаются международные Конвенции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>Параметры

*CharType*<br/>
Тип, используемый внутри программы для кодирования символов.

*Intl*<br/>
Флаг, указывающий, должны ли соблюдаться международные конвенции.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

Статический объект const intl хранит значение параметра-шаблона *Intl*.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[moneypunct](#moneypunct)|Конструктор объектов типа `moneypunct`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[string_type](#string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[curr_symbol](#curr_symbol)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.|
|[decimal_point](#decimal_point)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.|
|[do_curr_symbol](#do_curr_symbol)|Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.|
|[do_decimal_point](#do_decimal_point)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.|
|[do_frac_digits](#do_frac_digits)|Защищенная виртуальная функция-член возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.|
|[do_grouping](#do_grouping)|Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|
|[do_neg_format](#do_neg_format)|Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих отрицательные числа.|
|[do_negative_sign](#do_negative_sign)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака отрицательного числа.|
|[do_pos_format](#do_pos_format)|Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих положительные числа.|
|[do_positive_sign](#do_positive_sign)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака положительного числа.|
|[do_thousands_sep](#do_thousands_sep)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.|
|[frac_digits](#frac_digits)|Возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.|
|[grouping](#grouping)|Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|
|[neg_format](#neg_format)|Возвращает определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.|
|[negative_sign](#negative_sign)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.|
|[pos_format](#pos_format)|Возвращает определенное языковым стандартом правило форматирования выходных значений с положительными числами.|
|[positive_sign](#positive_sign)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.|
|[thousands_sep](#thousands_sep)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="char_type"></a>  moneypunct::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона **CharType**.

## <a name="curr_symbol"></a>  moneypunct::curr_symbol

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая символ валюты.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_curr_symbol](#do_curr_symbol).

### <a name="example"></a>Пример

```cpp
// moneypunct_curr_symbol.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct < char, true > &mpunct = use_facet < moneypunct < char, true > >(loc);
   cout << loc.name( ) << " international currency symbol "<<  mpunct.curr_symbol( ) << endl;

   const moneypunct < char, false> &mpunct2 = use_facet < moneypunct < char, false> >(loc);
   cout << loc.name( ) << " domestic currency symbol "<<  mpunct2.curr_symbol( ) << endl;
};
```

## <a name="decimal_point"></a>  moneypunct::decimal_point

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_decimal_point](#do_decimal_point).

### <a name="example"></a>Пример

```cpp
// moneypunct_decimal_pt.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc("german_germany");

   const moneypunct < char, true > &mpunct = use_facet
      < moneypunct < char, true > >(loc);
   cout << loc.name( ) << " international decimal point "
        << mpunct.decimal_point( ) << endl;

   const moneypunct < char, false> &mpunct2 = use_facet
      < moneypunct < char, false> >(loc);
   cout << loc.name( ) << " domestic decimal point "
        << mpunct2.decimal_point( ) << endl;
}
```

```Output
German_Germany.1252 international decimal point ,
German_Germany.1252 domestic decimal point ,
```

## <a name="do_curr_symbol"></a>  moneypunct::do_curr_symbol

Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.

```cpp
virtual string_type do_curr_symbol() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [curr_symbol](#curr_symbol), где виртуальная функция-член вызывается из `curr_symbol`.

## <a name="do_decimal_point"></a>  moneypunct::do_decimal_point

Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [decimal_point](#decimal_point), где виртуальная функция-член вызывается из `decimal_point`.

## <a name="do_frac_digits"></a>  moneypunct::do_frac_digits

Защищенная виртуальная функция-член, которая возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [frac_digits](#frac_digits), где виртуальная функция-член вызывается из `frac_digits`.

## <a name="do_grouping"></a>  moneypunct::do_grouping

Защищенная виртуальная функция-член, которая возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

### <a name="example"></a>Пример

См. в примере [группирования](#grouping), где виртуальная функция-член вызывается из `grouping`.

## <a name="do_neg_format"></a>  moneypunct::do_neg_format

Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих отрицательные числа.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило формирования денежного поля вывода для отрицательного значения. Каждый из четырех элементов `pattern::field` может иметь значения:

- `none` для соответствия нулю или более пробелам или формирования пустого значения.

- `sign` для соответствия или формирования положительный или отрицательный знак.

- `space` для соответствия нулю или более пробелам или для формирования пробела.

- `symbol` для соответствия или формирования символа валюты.

- `value` для соответствия или формирования денежного значения.

Компоненты денежного поля вывода создаются и компонентов денежного поля ввода сопоставляются в порядке, в котором эти элементы появляются в `pattern::field`. Каждое из значений `sign`, `symbol`, `value`и либо `none` или `space` должно встречаться ровно один раз. Значение `none` не должно быть первым. Значение space **не должно** быть первым или последним. Если `Intl` имеет значение true, порядок не `symbol`, `sign`, `none`, затем `value`.

Версия-шаблон `moneypunct`\< **CharType**, **Intl**> возвращает `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Пример

См. пример для [neg_format](#neg_format), где виртуальная функция-член вызывается из `neg_format`.

## <a name="do_negative_sign"></a>  moneypunct::do_negative_sign

Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака отрицательного числа.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.

### <a name="example"></a>Пример

См. пример для [negative_sign](#negative_sign), где виртуальная функция-член вызывается из `negative_sign`.

## <a name="do_pos_format"></a>  moneypunct::do_pos_format

Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих положительные числа.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило формирования денежного поля вывода для положительного значения. (Она также определяет способ сопоставления компонентов денежного поля ввода.) Кодирование такое же, как для [do_neg_format](#do_neg_format).

Версия-шаблон moneypunct\< **CharType**, **Inputlterator**> возвращает `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Пример

См. пример для [pos_format](#pos_format), где виртуальная функция-член вызывается из `pos_format`.

## <a name="do_positive_sign"></a>  moneypunct::do_positive_sign

Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного значения.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа положительного значения.

### <a name="example"></a>Пример

См. пример для [positive_sign](#positive_sign), где виртуальная функция-член вызывается из `positive_sign`.

## <a name="do_thousands_sep"></a>  moneypunct::do_thousands_sep

Защищенная виртуальная функция-член, которая возвращает определенный языковым стандартом элемент для использования в качестве разделителя групп цифр слева от любого десятичного разделителя.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент определенного языкового стандарта для использования в качестве разделителя групп слева от любого десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [thousands_sep](#thousands_sep), где виртуальная функция-член вызывается из `thousands_sep`.

## <a name="frac_digits"></a>  moneypunct::frac_digits

Возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_frac_digits](#do_frac_digits).

### <a name="example"></a>Пример

```cpp
// moneypunct_frac_digits.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true> >(loc);
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " international frac_digits\n to the right"
        << " of the radix character: "
        << mpunct.frac_digits ( ) << endl << endl;

   const moneypunct <char, false> &mpunct2 =
       use_facet <moneypunct <char, false> >(loc);
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " domestic grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct2.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " domestic frac_digits\n to the right"
        << " of the radix character: "
        << mpunct2.frac_digits ( ) << endl << endl;
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 international frac_digits
to the right of the radix character: 2

German_Germany.1252 domestic grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 domestic frac_digits
to the right of the radix character: 2
```

## <a name="grouping"></a>  moneypunct::grouping

Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

```cpp
string grouping() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_grouping](#do_grouping).

### <a name="example"></a>Пример

```cpp
// moneypunct_grouping.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true> >( loc );
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " international frac_digits\n to the right"
        << " of the radix character: "
        << mpunct.frac_digits ( ) << endl << endl;

   const moneypunct <char, false> &mpunct2 =
       use_facet <moneypunct <char, false> >( loc );
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " domestic grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct2.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " domestic frac_digits\n to the right"
        << " of the radix character: "
        << mpunct2.frac_digits ( ) << endl << endl;
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 international frac_digits
to the right of the radix character: 2

German_Germany.1252 domestic grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 domestic frac_digits
to the right of the radix character: 2
```

## <a name="moneypunct"></a>  moneypunct::moneypunct

Конструктор объектов типа `moneypunct`.

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_Refs*<br/>
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения *_Refs* параметра и их важность:

- 0: Время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: Время существования объекта должно управляться вручную.

- \> 1: Эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект с [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="neg_format"></a>  moneypunct::neg_format

Возвращает определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_neg_format](#do_neg_format).

### <a name="example"></a>Пример

```cpp
// moneypunct_neg_format.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( ) {
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international negative number format: "
        << mpunct.neg_format( ).field[0]
        << mpunct.neg_format( ).field[1]
        << mpunct.neg_format( ).field[2]
        << mpunct.neg_format( ).field[3] << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic negative number format: "
        << mpunct2.neg_format( ).field[0]
        << mpunct2.neg_format( ).field[1]
        << mpunct2.neg_format( ).field[2]
        << mpunct2.neg_format( ).field[3] << endl;
}
```

## <a name="negative_sign"></a>  moneypunct::negative_sign

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.

```cpp
string_type negative_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_negative_sign](#do_negative_sign).

### <a name="example"></a>Пример

```cpp
// moneypunct_neg_sign.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true> >(loc);
   cout << loc.name( ) << " international negative sign: "
        << mpunct.negative_sign( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic negative sign: "
        << mpunct2.negative_sign( ) << endl;

   locale loc2( "French" );

   const moneypunct <char, true> &mpunct3 =
      use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international negative sign: "
        << mpunct3.negative_sign( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic negative sign: "
        << mpunct4.negative_sign( ) << endl;
};
```

```Output
German_Germany.1252 international negative sign: -
German_Germany.1252 domestic negative sign: -
French_France.1252 international negative sign: -
French_France.1252 domestic negative sign: -
```

## <a name="pos_format"></a>  moneypunct::pos_format

Возвращает определенное языковым стандартом правило форматирования выходных значений с положительными числами.

```cpp
pattern pos_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило форматирования выходных значений с положительными числами.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_pos_format](#do_pos_format).

### <a name="example"></a>Пример

```cpp
// moneypunct_pos_format.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main() {
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true> >(loc);
   cout << loc.name( ) << " international positive number format: "
        << mpunct.pos_format( ).field[0]
        << mpunct.pos_format( ).field[1]
        << mpunct.pos_format( ).field[2]
        << mpunct.pos_format( ).field[3] << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic positive number format: "
        << mpunct2.pos_format( ).field[0]
        << mpunct2.pos_format( ).field[1]
        << mpunct2.pos_format( ).field[2]
        << mpunct2.pos_format( ).field[3] << endl;
}
```

## <a name="positive_sign"></a>  moneypunct::positive_sign

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.

```cpp
string_type positive_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_positive_sign](#do_positive_sign).

### <a name="example"></a>Пример

```cpp
// moneypunct_pos_sign.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international positive sign:"
        << mpunct.positive_sign( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic positive sign:"
        << mpunct2.positive_sign( ) << endl;

   locale loc2( "French" );

   const moneypunct <char, true> &mpunct3 =
      use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international positive sign:"
        << mpunct3.positive_sign( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic positive sign:"
        << mpunct4.positive_sign( ) << endl;
};
```

```Output
German_Germany.1252 international positive sign:
German_Germany.1252 domestic positive sign:
French_France.1252 international positive sign:
French_France.1252 domestic positive sign:
```

## <a name="string_type"></a>  moneypunct::string_type

Тип, который описывает строку, содержащую символы типа **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию класса-шаблона [basic_string](../standard-library/basic-string-class.md), объекты которого могут хранить копии последовательности знаков препинания.

## <a name="thousands_sep"></a>  moneypunct::thousands_sep

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_thousands_sep](#do_thousands_sep).

### <a name="example"></a>Пример

```cpp
// moneypunct_thou_sep.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international thousands separator: "
        << mpunct.thousands_sep( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic thousands separator: "
        << mpunct2.thousands_sep( ) << endl << endl;

   locale loc2( "english_canada" );

   const moneypunct <char, true> &mpunct3 =
       use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international thousands separator: "
        << mpunct3.thousands_sep( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic thousands separator: "
        << mpunct4.thousands_sep( ) << endl;
}
```

```Output
German_Germany.1252 international thousands separator: .
German_Germany.1252 domestic thousands separator: .

English_Canada.1252 international thousands separator: ,
English_Canada.1252 domestic thousands separator: ,
```

## <a name="see-also"></a>См. также

[\<locale>](../standard-library/locale.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
