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
ms.openlocfilehash: 3a277b2f97fd53c52b705051c30eb18faf6364d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366251"
---
# <a name="moneypunct-class"></a>Класс moneypunct

Шаблон класса описывает объект, который может служить в качестве аспекта локализации для описания последовательностей типа *CharType,* используемых для представления поля ввода денежных данных или денежного поля вывода. Если параметр шаблона *Intl* *верен,* соблюдаются международные конвенции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов.

*Международный*\
Флаг, указывающий, должны ли соблюдаться международные конвенции.

## <a name="remarks"></a>Remarks

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

### <a name="member-functions"></a>Функции элементов

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
|[Группировки](#grouping)|Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|
|[neg_format](#neg_format)|Возвращает определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.|
|[negative_sign](#negative_sign)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.|
|[pos_format](#pos_format)|Возвращает определенное языковым стандартом правило форматирования выходных значений с положительными числами.|
|[positive_sign](#positive_sign)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.|
|[thousands_sep](#thousands_sep)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="moneypunctchar_type"></a><a name="char_type"></a>moneypunct::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом для параметра-шаблона **Chartype**.

## <a name="moneypunctcurr_symbol"></a><a name="curr_symbol"></a>moneypunct::curr_symbol

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая символ валюты.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctdecimal_point"></a><a name="decimal_point"></a>moneypunct::decimal

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctdo_curr_symbol"></a><a name="do_curr_symbol"></a>moneypunct::do'curr'symbol

Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.

```cpp
virtual string_type do_curr_symbol() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [curr_symbol](#curr_symbol), где виртуальная функция-член вызывается из `curr_symbol`.

## <a name="moneypunctdo_decimal_point"></a><a name="do_decimal_point"></a>moneypunct::do-decimal

Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [decimal_point](#decimal_point), где виртуальная функция-член вызывается из `decimal_point`.

## <a name="moneypunctdo_frac_digits"></a><a name="do_frac_digits"></a>moneypunct::do'frac-digits

Защищенная виртуальная функция-член, которая возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [frac_digits](#frac_digits), где виртуальная функция-член вызывается из `frac_digits`.

## <a name="moneypunctdo_grouping"></a><a name="do_grouping"></a>moneypunct::do-grouping

Защищенная виртуальная функция-член, которая возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

### <a name="example"></a>Пример

См пример для [группировки,](#grouping)где виртуальная `grouping`функция члена вызывается .

## <a name="moneypunctdo_neg_format"></a><a name="do_neg_format"></a>moneypunct::do-neg

Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих отрицательные числа.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило формирования денежного поля вывода для отрицательного значения. Каждый из четырех `pattern::field` элементов может иметь значения:

- `none`соответствовать нулю или больше пробелов или ничего не генерировать.

- `sign`для соответствия или создания положительного или отрицательного знака.

- `space`для сопоставления нуля или более пробелов или создания пространства.

- `symbol`для соответствия или создания символа валюты.

- `value`для сопоставления или создания денежной стоимости.

Компоненты денежного поля вывода генерируются и компоненты денежного ввода поля `pattern::field`сопоставляются в порядке, в котором эти элементы появляются в . Каждое из `sign`значений, `symbol` `value`, `none` `space` , и либо или должны появиться ровно один раз. Значение `none` не должно отображаться первым. Значение space **не должно** быть первым или последним. Если `Intl` это правда, `symbol`порядок, `sign` `none` `value`то .

Версия-шаблон `moneypunct`\< **CharType**, **Intl**> возвращает `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Пример

См. пример для [neg_format](#neg_format), где виртуальная функция-член вызывается из `neg_format`.

## <a name="moneypunctdo_negative_sign"></a><a name="do_negative_sign"></a>moneypunct::do'негативного знака

Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака отрицательного числа.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.

### <a name="example"></a>Пример

См. пример для [negative_sign](#negative_sign), где виртуальная функция-член вызывается из `negative_sign`.

## <a name="moneypunctdo_pos_format"></a><a name="do_pos_format"></a>moneypunct::do-pos-формат

Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих положительные числа.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило формирования денежного поля вывода для положительного значения. (Он также определяет, как сопоставить компоненты поля денежных вводимых вод.) Кодирование такое же, как и для [do_neg_format.](#do_neg_format)

Версия-шаблон moneypunct\< **CharType**, **Inputlterator**> возвращает `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Пример

См. пример для [pos_format](#pos_format), где виртуальная функция-член вызывается из `pos_format`.

## <a name="moneypunctdo_positive_sign"></a><a name="do_positive_sign"></a>moneypunct::do-положительный знак

Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного значения.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа положительного значения.

### <a name="example"></a>Пример

См. пример для [positive_sign](#positive_sign), где виртуальная функция-член вызывается из `positive_sign`.

## <a name="moneypunctdo_thousands_sep"></a><a name="do_thousands_sep"></a>moneypunct::do-thousands

Защищенная виртуальная функция-член, которая возвращает определенный языковым стандартом элемент для использования в качестве разделителя групп цифр слева от любого десятичного разделителя.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент определенного языкового стандарта для использования в качестве разделителя групп слева от любого десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [thousands_sep](#thousands_sep), где виртуальная функция-член вызывается из `thousands_sep`.

## <a name="moneypunctfrac_digits"></a><a name="frac_digits"></a>moneypunct::frac_digits

Возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctgrouping"></a><a name="grouping"></a>moneypunct::grouping

Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

```cpp
string grouping() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctmoneypunct"></a><a name="moneypunct"></a>moneypunct::moneypunct

Конструктор объектов типа `moneypunct`.

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Remarks

Возможные значения для *параметра _Refs* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: Эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект с [помощью локализации::facet](../standard-library/locale-class.md#facet_class) *(я. Рефы).*

## <a name="moneypunctneg_format"></a><a name="neg_format"></a>moneypunct::neg_format

Возвращает определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctnegative_sign"></a><a name="negative_sign"></a>moneypunct::negative_sign

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.

```cpp
string_type negative_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctpos_format"></a><a name="pos_format"></a>moneypunct::pos-format

Возвращает определенное языковым стандартом правило форматирования выходных значений с положительными числами.

```cpp
pattern pos_format() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило форматирования выходных значений с положительными числами.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctpositive_sign"></a><a name="positive_sign"></a>moneypunct::positive

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.

```cpp
string_type positive_sign() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.

### <a name="remarks"></a>Remarks

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

## <a name="moneypunctstring_type"></a><a name="string_type"></a>moneypunct::string_type

Тип, который описывает строку символов типа **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [basic_string](../standard-library/basic-string-class.md) объекты которых могут хранить копии последовательностей знаков препинания.

## <a name="moneypunctthousands_sep"></a><a name="thousands_sep"></a>moneypunct::thousands_sep

Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.

### <a name="remarks"></a>Remarks

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

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
