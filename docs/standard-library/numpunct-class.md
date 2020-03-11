---
title: Класс numpunct
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct
- xlocnum/std::numpunct::char_type
- xlocnum/std::numpunct::string_type
- xlocnum/std::numpunct::decimal_point
- xlocnum/std::numpunct::do_decimal_point
- xlocnum/std::numpunct::do_falsename
- xlocnum/std::numpunct::do_grouping
- xlocnum/std::numpunct::do_thousands_sep
- xlocnum/std::numpunct::do_truename
- xlocnum/std::numpunct::falsename
- xlocnum/std::numpunct::grouping
- xlocnum/std::numpunct::thousands_sep
- xlocnum/std::numpunct::truename
helpviewer_keywords:
- std::numpunct [C++]
- std::numpunct [C++], char_type
- std::numpunct [C++], string_type
- std::numpunct [C++], decimal_point
- std::numpunct [C++], do_decimal_point
- std::numpunct [C++], do_falsename
- std::numpunct [C++], do_grouping
- std::numpunct [C++], do_thousands_sep
- std::numpunct [C++], do_truename
- std::numpunct [C++], falsename
- std::numpunct [C++], grouping
- std::numpunct [C++], thousands_sep
- std::numpunct [C++], truename
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
ms.openlocfilehash: 07285f5c014db1ddf419c372913cac0364538a55
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856632"
---
# <a name="numpunct-class"></a>Класс numpunct

Шаблон класса, описывающий объект, который может служить локальным аспектом для описания последовательностей типа `CharType` используемое для представления сведений о форматировании и пунктуации числовых и логических выражений.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class numpunct : public locale::facet;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов в языковом стандарте.

## <a name="remarks"></a>Remarks

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Description|
|-|-|
|[numpunct](#numpunct)|Конструктор для объектов типа `numpunct`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Description|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[string_type](#string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Description|
|-|-|
|[decimal_point](#decimal_point)|Возвращает элемент определенного языкового стандарта для использования в качестве десятичного разделителя.|
|[do_decimal_point](#do_decimal_point)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве десятичного разделителя.|
|[do_falsename](#do_falsename)|Защищенная виртуальная функция-член, которая вызывается для возврата строки, используемой в качестве текстового представления значения **false**.|
|[do_grouping](#do_grouping)|Защищенная виртуальная функция-член, вызываемая для того, чтобы возвратить определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|
|[do_thousands_sep](#do_thousands_sep)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве разделителя тысяч.|
|[do_truename](#do_truename)|Защищенная виртуальная функция-член, вызываемая для возврата строки, которая будет использоваться как текстовое представление значения **true**.|
|[falsename](#falsename)|Возвращает строку, которая будет использоваться как текстовое представление значения **false**.|
|[grouping](#grouping)|Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|
|[thousands_sep](#thousands_sep)|Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.|
|[truename](#truename)|Возвращает строку, которая будет использоваться как текстовое представление значения **true**.|

## <a name="requirements"></a>Требования

**Заголовок:** \<языковой стандарт >

**Пространство имен:** std

## <a name="char_type"></a>  numpunct::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом для параметра-шаблона **Chartype.**

## <a name="decimal_point"></a>  numpunct::decimal_point

Возвращает элемент определенного языкового стандарта для использования в качестве десятичного разделителя.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент определенного языкового стандарта для использования в качестве десятичного разделителя.

### <a name="remarks"></a>Remarks

Функция-член возвращает [do_decimal_point](#do_decimal_point).

### <a name="example"></a>Пример

```cpp
// numpunct_decimal_point.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const numpunct <char> &npunct =
   use_facet <numpunct <char> >( loc);
   cout << loc.name( ) << " decimal point "<<
   npunct.decimal_point( ) << endl;
   cout << loc.name( ) << " thousands separator "
   << npunct.thousands_sep( ) << endl;
};
```

```Output
German_Germany.1252 decimal point ,
German_Germany.1252 thousands separator .
```

## <a name="do_decimal_point"></a>  numpunct::do_decimal_point

Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве десятичного разделителя.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент определенного языкового стандарта для использования в качестве десятичного разделителя.

### <a name="example"></a>Пример

См. пример для [decimal_point](#decimal_point), где виртуальная функция-член вызывается из `decimal_point`.

## <a name="do_falsename"></a>  numpunct::do_falsename

Защищенная виртуальная функция-член возвращает последовательность, которая будет использоваться как текстовое представление значения **false**.

```cpp
virtual string_type do_falsename() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая последовательность для использования в качестве текстового представления значения **false**.

### <a name="remarks"></a>Remarks

Функция-член возвращает строку false для представления значения **false** во всех языковых стандартах.

### <a name="example"></a>Пример

См. пример для [falsename](#falsename), где виртуальная функция-член вызывается из `falsename`.

## <a name="do_grouping"></a>  numpunct::do_grouping

Защищенная виртуальная функция-член, вызываемая для того, чтобы возвратить определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Возвращаемое значение

Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.

### <a name="remarks"></a>Remarks

Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя. Кодирование такое же, как для **lconv::grouping**.

### <a name="example"></a>Пример

См. пример для [группирования](#grouping), где виртуальная функция-член вызывается `grouping`.

## <a name="do_thousands_sep"></a>  numpunct::do_thousands_sep

Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве разделителя тысяч.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.

### <a name="remarks"></a>Remarks

Защищенная виртуальная функция-член возвращает элемент типа `CharType`, зависящий от языкового стандарта, для использования в качестве разделителя групп слева от любой десятичной запятой.

### <a name="example"></a>Пример

См. пример для [thousands_sep](#thousands_sep), где виртуальная функция-член вызывается из `thousands_sep`.

## <a name="do_truename"></a>  numpunct::do_truename

Защищенная виртуальная функция-член, вызываемая для возврата строки, которая будет использоваться как текстовое представление значения **true**.

```cpp
virtual string_type do_truename() const;
```

### <a name="remarks"></a>Remarks

Строка, которая будет использоваться как текстовое представление значения **true**.

Все языковые стандарты возвращают строку true для представления значения **true**.

### <a name="example"></a>Пример

См. пример для [truename](#truename), где виртуальная функция-член вызывается из `truename`.

## <a name="falsename"></a>  numpunct::falsename

Возвращает строку, которая будет использоваться как текстовое представление значения **false**.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая последовательность `CharType`s для использования в качестве текстового представления значения **false**.

### <a name="remarks"></a>Remarks

Функция-член возвращает строку false для представления значения **false** во всех языковых стандартах.

Функция-член возвращает [do_falsename](#do_falsename).

### <a name="example"></a>Пример

```cpp
// numpunct_falsename.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "English" );

   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;

   locale loc2( "French" );
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;
}
```

```Output
English_United States.1252 truename true
English_United States.1252 falsename false
French_France.1252 truename true
French_France.1252 falsename false
```

## <a name="grouping"></a>  numpunct::grouping

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
// numpunct_grouping.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany");

   const numpunct <char> &npunct =
       use_facet < numpunct <char> >( loc );
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(npunct.grouping ( )[i])
           << endl;
   }
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
```

## <a name="numpunct"></a>  numpunct::numpunct

Конструктор для объектов типа `numpunct`.

```cpp
explicit numpunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Remarks

Возможные значения параметра *_Refs* и их значимость:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \> 1: эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект с **языковым стандартом::** [Facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="string_type"></a>  numpunct::string_type

Тип, который описывает строку, содержащую символы типа **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Remarks

Тип описывает специализацию шаблона класса [basic_string](../standard-library/basic-string-class.md) , объекты которой могут хранить копии последовательностей пунктуации.

## <a name="thousands_sep"></a>  numpunct::thousands_sep

Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.

### <a name="remarks"></a>Remarks

Функция-член возвращает [do_thousands_sep](#do_thousands_sep).

### <a name="example"></a>Пример

```cpp
// numpunct_thou_sep.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const numpunct <char> &npunct =
   use_facet < numpunct < char > >( loc );
   cout << loc.name( ) << " decimal point "<<
   npunct.decimal_point( ) << endl;
   cout << loc.name( ) << " thousands separator "
   << npunct.thousands_sep( ) << endl;
};
```

```Output
German_Germany.1252 decimal point ,
German_Germany.1252 thousands separator .
```

## <a name="truename"></a>  numpunct::truename

Возвращает строку, которая будет использоваться как текстовое представление значения **true**.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, которая будет использоваться как текстовое представление значения **true**.

### <a name="remarks"></a>Remarks

Функция-член возвращает [do_truename](#do_truename).

Все языковые стандарты возвращают строку true для представления значения **true**.

### <a name="example"></a>Пример

```cpp
// numpunct_truename.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "English" );

   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;

   locale loc2("French");
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;
}
```

```Output
English_United States.1252 truename true
English_United States.1252 falsename false
French_France.1252 truename true
French_France.1252 falsename false
```

## <a name="see-also"></a>См. также раздел

[\<locale>](../standard-library/locale.md)\
[Класс facet](../standard-library/locale-class.md#facet_class)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
