---
title: Класс locale | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocale/std::locale
- xlocale/std::locale::category
- xlocale/std::locale::combine
- xlocale/std::locale::name
- xlocale/std::locale::classic
- xlocale/std::locale::global
- xlocale/std::locale::operator( )
- xlocale/std::locale::facet
- xlocale/std::locale::id
dev_langs:
- C++
helpviewer_keywords:
- std::locale [C++]
- std::locale [C++], category
- std::locale [C++], combine
- std::locale [C++], name
- std::locale [C++], classic
- std::locale [C++], global
- std::locale [C++], facet
- std::locale [C++], id
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80cb3dd5d60665fbfb510fb2fddf94f17ef9f171
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963798"
---
# <a name="locale-class"></a>Класс locale

Класс, описывающий объект языкового стандарта, инкапсулирующий данные по соответствующей культуре в качестве набора аспектов, которые собирательно определяют ту или иную локализованную среду.

## <a name="syntax"></a>Синтаксис

```cpp
class locale;
```

## <a name="remarks"></a>Примечания

Аспект — это указатель на объект класса, выведенного производным от класса [facet](#facet_class), который обладает общим объектом в формате:

```cpp
static locale::id id;
```

Можно задать открытый набор данных аспектов. Можно также создать объект языкового стандарта, назначающий произвольное количество аспектов.

Предопределенные группы этих аспектов представляют [категории языкового стандарта](#category), которыми в стандартной библиотеке C традиционно управляет функция `setlocale`.

Категория collate (LC_COLLATE) включает аспекты:

```cpp
collate<char>
collate<wchar_t>
```

Категория ctype (LC_CTYPE) включает аспекты:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Категория monetary (LC_MONETARY) включает аспекты:

```cpp
moneypunct<char, false>
moneypunct<wchar_t, false>
moneypunct<char, true>
moneypunct<wchar_t, true>
money_get<char, istreambuf_iterator<char>>
money_get<wchar_t, istreambuf_iterator<wchar_t>>
money_put<char, ostreambuf_iterator<char>>
money_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Категория numeric (LC_NUMERIC) включает аспекты:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Категория time (LC_TIME) включает аспекты:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Категория messages (LC_MESSAGES) включает аспекты:

```cpp
messages<char>
messages<wchar_t>
```

(Последняя категория необходима Posix для, но не стандартной библиотеке C).

Некоторые из этих предопределенных аспектов используются классами iostreams для управления преобразованием числовых значений в текстовые последовательности и наоборот.

Объект класса locale также сохраняет имя языкового стандарта в качестве объекта класса [string](../standard-library/string-typedefs.md#string). Использование недопустимого имени языкового стандарта для создания аспекта языкового стандарта или объекта языкового стандарта создает объект класса [runtime_error](../standard-library/runtime-error-class.md). Сохраненное имя языкового стандарта — `"*"`, если объект языкового стандарта не может быть уверен в том, что локальный стандарт языка C точно соответствует представленному данным объектом. В противном случае можно установить соответствующий языковой стандарт в стандартной библиотеке C, для объекта языкового стандарта `Loc`, путем вызова `setlocale`(LC_ALL `,` `Loc`. [name](#name)`().c_str()`).

В данном случае можно также вызвать статическую функцию-член:

```cpp
static locale empty();
```

создать объект языкового стандарта без аспектов. Это также прозрачный языковой стандарт; если функции-шаблоны [has_facet](../standard-library/locale-functions.md#has_facet) и [use_facet](../standard-library/locale-functions.md#use_facet) не могут найти запрошенный аспект в прозрачном языковом стандарте, они в первую очередь обращаются к глобальному языковому стандарту, а затем, если таковой является прозрачным, к классическому языковому стандарту. Таким образом, можно написать:

```cpp
cout.imbue(locale::empty());
```

Последующие вставки в [cout](../standard-library/iostream.md#cout) облегчаются текущим состоянием глобального языкового стандарта. Можно даже написать:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Числовые правила форматирования для последующих вставок в `cout` остаются такими же, как в языковом стандарте C, даже если глобальный языковой стандарт предоставляет другие правила вставки дат и денежных сумм.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[locale](#locale)|Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание:|
|-|-|
|[category](#category)|Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
|-|-|
|[combine](#combine)|Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.|
|[name](#name)|Возвращает имя сохраненного языкового стандарта.|

### <a name="static-functions"></a>Статические функции

|||
|-|-|
|[classic](#classic)|Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.|
|[global](#global)|Сброс языкового стандарта программы по умолчанию.|

### <a name="operators"></a>Операторы

|Оператор|Описание:|
|-|-|
|[оператор!=](#op_neq)|Проверка двух языковых стандартов на неравенство.|
|[оператор( )](#op_call)|Сравнивает два объекта `basic_string`.|
|[оператор==](#op_eq_eq)|Проверка двух языковых стандартов на равенство.|

### <a name="classes"></a>Классы

|Класс|Описание:|
|-|-|
|[facet](#facet_class)|Класс, используемый как базовый класс для всех аспектов языкового стандарта.|
|[id](#id_class)|Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="category"></a>  locale::category

Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.

```cpp
typedef int category;
static const int collate = LC_COLLATE;
static const int ctype = LC_CTYPE;
static const int monetary = LC_MONETARY;
static const int numeric = LC_NUMERIC;
static const int time = LC_TIME;
static const int messages = LC_MESSAGES;
static const int all = LC_ALL;
static const int none = 0;
```

### <a name="remarks"></a>Примечания

Тип является синонимом **int** тип, который может представлять группу различающихся элементов Битовая маска, введите локальный для класса языкового стандарта, или может использоваться для представления любой из соответствующих категорий языкового стандарта C. Элементы:

- `collate`, соответствующее категории lc_collate в с

- `ctype`, соответствующее категории LC_CTYPE

- `monetary`, соответствующее категории lc_monetary в с

- `numeric`, соответствующее категории lc_numeric в с

- `time`, соответствующее категории lc_time в с

- `messages`, соответствующий Posix категории LC_MESSAGES

Кроме того, есть два полезных значения:

- `none`, соответствующий ни одна из категорий C

- `all`, соответствующий объединению всех категорий LC_ALL

Можно обозначить произвольную группу категорий с помощью `OR` эти константы, как и в `monetary` &#124; `time`.

## <a name="classic"></a>  locale::classic

Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на языковой стандарт C.

### <a name="remarks"></a>Примечания

Классический языковой стандарт в C — U.S. English ASCII в стандартной библиотеке C. Он по умолчанию используется в программах, которые не поддерживают локализацию.

### <a name="example"></a>Пример

```cpp
// locale_classic.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: " << loc2.name( )
        << "." << endl;
   cout << "The name of the current locale is: " << loc1.name( )
        << "." << endl;

   if (loc2 == locale::classic( ) )
      cout << "The previous locale was classic." << endl;
   else
      cout << "The previous locale was not classic." << endl;

   if (loc1 == locale::classic( ) )
      cout << "The current locale is classic." << endl;
   else
      cout << "The current locale is not classic." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
The previous locale was classic.
The current locale is not classic.
```

## <a name="combine"></a>  locale::combine

Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.

```cpp
template <class Facet>
locale combine(const locale& Loc) const;
```

### <a name="parameters"></a>Параметры

*Loc* языковой стандарт, содержащий аспект для вставки в целевой языковой стандарт.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает объект языкового стандарта, замену в или добавление к  **\*это** аспекта `Facet` в *Loc*.

### <a name="example"></a>Пример

```cpp
// locale_combine.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;
}
```

## <a name="facet_class"></a>  Класс facet

Класс, используемый как базовый класс для всех аспектов языкового стандарта.

```cpp
class facet {
protected:
    explicit facet(size_t _Refs = 0);
   virtual ~facet();
private:
   facet(const facet&)
   // not defined void operator=(const facet&)
     // not defined
};
```

### <a name="remarks"></a>Примечания

Обратите внимание, что объект класса аспект нельзя копировать или присваивать. Можно создавать и удалять объекты, производные от класса `locale::facet`, но не объекты правильного базового класса. Как правило, объект `_Myfac`, производный от аспекта, создается создании языкового стандарта, как в **localeloc**( `locale::classic`( ), **new**`_Myfac`);

В таких случаях конструктор для базового класса аспекта должен иметь нулевое значение аргумента `_Refs`. Когда объект больше не нужен, он удаляется. Таким образом, необходимо указывать ненулевое значение аргумента _ *Refs* только в тех редких случаях, когда вы отвечаете за время жизни объекта.

## <a name="global"></a>  locale::global

Сброс языкового стандарта по умолчанию для программы. Это влияет на глобальный языковой стандарт C и C++.

```cpp
static locale global(const locale& Loc);
```

### <a name="parameters"></a>Параметры

*Loc* языкового стандарта для использования в качестве языкового стандарта по умолчанию с помощью программы.

### <a name="return-value"></a>Возвращаемое значение

Языковой стандарт до сброса языкового стандарта по умолчанию.

### <a name="remarks"></a>Примечания

При запуске программы глобальный языковой стандарт совпадает в классическим языковым стандартом. Функция `global()` вызывает `setlocale( LC_ALL, loc.name. c_str())` для установки соответствующего языкового стандарта в стандартной библиотеке C.

### <a name="example"></a>Пример

```cpp
// locale_global.cpp
// compile by using: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   locale loc1;
   cout << "The initial locale is: " << loc1.name( ) << endl;
   locale loc2 = locale::global ( loc );
   locale loc3;
   cout << "The current locale is: " << loc3.name( ) << endl;
   cout << "The previous locale was: " << loc2.name( ) << endl;
}
```

```Output
The initial locale is: C
The current locale is: German_Germany.1252
The previous locale was: C
```

## <a name="id_class"></a>  Класс id

Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.

class id { protected:    id(); private:    id(const id&) // not defined void operator=(const id&)  // not defined    };

### <a name="remarks"></a>Примечания

Класс-член описывает статический объект-член, необходимый для каждого уникального аспекта языкового стандарта. Обратите внимание, что нельзя копировать или присвоить объект типа класса `id`.

## <a name="locale"></a>  locale::locale

Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта.

```cpp
locale();

explicit locale(const char* Locname, category Cat = all);
explicit locale(const string& Locname);
locale( const locale& Loc);
locale(const locale& Loc, const locale& Other, category Cat);
locale(const locale& Loc, const char* Locname, category Cat);

template <class Facet>
locale(const locale& Loc, const Facet* Fac);
```

### <a name="parameters"></a>Параметры

*Locname* имя языкового стандарта.

*Loc* языкового стандарта, который должен копироваться при создании нового языкового стандарта.

*Другие* языковой стандарт, из которого необходимо выбрать категорию.

*CAT* категории для замены в созданном языковом стандарте.

*FAc* аспект для замены в созданном языковом стандарте.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует объект для соответствия глобальному языковому стандарту. Второй и третий конструкторы инициализируют все категории языкового стандарта, чтобы их поведение согласовалось имя языкового стандарта *Locname*. Оставшиеся конструкторы копируют *Loc*, за исключением следующего:

`locale(const locale& Loc, const locale& Other, category Cat);`

заменяет из *других* аспекты, соответствующее категории C, для которой C & *Cat* имеет ненулевое значение.

`locale(const locale& Loc, const char* Locname, category Cat);`

`locale(const locale& Loc, const string& Locname, category Cat);`

заменяет из `locale(Locname, _All)` аспекты, соответствующее категории C, для которой C & *Cat* имеет ненулевое значение.

`template<class Facet> locale(const locale& Loc, Facet* Fac);`

заменяет в (или добавляет) *Loc* аспекта *Fac*, если *Fac* не является пустым указателем.

Если имя языкового стандарта *Locname* является пустым указателем или недопустимо, функция создает [runtime_error](../standard-library/runtime-error-class.md).

### <a name="example"></a>Пример

```cpp
// locale_locale.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( ) {

   // Second constructor
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   // The first (default) constructor
   locale loc2;
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   // Third constructor
   locale loc3 (loc2,loc, _M_COLLATE );
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;

   // Fourth constructor
   locale loc4 (loc2, "German_Germany", _M_COLLATE );
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;
}
```

## <a name="name"></a>  locale::name

Возвращает имя сохраненного языкового стандарта.

```cpp
string name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, задающая имя языкового стандарта.

### <a name="example"></a>Пример

```cpp
// locale_name.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: "
        << loc2.name( ) << "." << endl;
   cout << "The name of the current locale is: "
        << loc1.name( ) << "." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
```

## <a name="op_neq"></a>  locale::operator!=

Проверка двух языковых стандартов на неравенство.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Параметры

*правом* один из языковых стандартов на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, равное **true**, если языковые стандарты не являются копиями одного и того же языкового стандарта; в противном случае **false**.

### <a name="remarks"></a>Примечания

Языковые стандарты считаются равными, если они - один и тот же языковой стандарт, если один из них является копией другого, или если они имеют одинаковые имена.

### <a name="example"></a>Пример

```cpp
// locale_op_ne.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 != loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;

   if ( loc1 != loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;
}
```

```Output
locales loc1 (German_Germany.1252) and
 loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252) and
 loc3 (English_United States.1252) are not equal.
```

## <a name="op_call"></a>  locale::operator()

Сравнивает два объекта `basic_string`.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Параметры

*слева* левая строка.

*правом* правая строка.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает:

- –1, если первая последовательность оказывается меньше, чем вторая;

- +1, если вторая последовательность оказывается меньше, чем первая;

- 0, если последовательности являются эквивалентными.

### <a name="remarks"></a>Примечания

Функция-член фактически выполняет:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Таким образом, объект языкового стандарта можно использовать как объект-функцию.

### <a name="example"></a>Пример

```cpp
// locale_op_compare.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

int main( )
{
   using namespace std;
   wchar_t *sa = L"ztesting";
   wchar_t *sb = L"\0x00DFtesting";
   basic_string<wchar_t> a( sa );
   basic_string<wchar_t> b( sb );

   locale loc( "German_Germany" );
   cout << loc( a,b ) << endl;

   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );
   cout << ( fac.compare( sa, sa + a.length( ),
       sb, sb + b.length( ) ) < 0) << endl;
}
```

```Output
0
0
```

## <a name="op_eq_eq"></a>  locale::operator==

Проверка двух языковых стандартов на равенство.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Параметры

*правом* один из языковых стандартов для проверки на равенство.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, равное **true**, если языковые стандарты являются копиями одного и того же языкового стандарта; в противном случае **false**.

### <a name="remarks"></a>Примечания

Языковые стандарты считаются равными, если они - один и тот же языковой стандарт, если один из них является копией другого, или если они имеют одинаковые имена.

### <a name="example"></a>Пример

```cpp
// locale_op_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 == loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."
      << endl;

   if ( loc1 == loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."
      << endl;
}
```

```Output
locales loc1 (German_Germany.1252)
 and loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252)
 and loc3 (English_United States.1252) are not equal.
```

## <a name="see-also"></a>См. также

[\<locale>](../standard-library/locale.md)<br/>
[Кодовые страницы](../c-runtime-library/code-pages.md)<br/>
[Имени языкового стандарта, языка и строк страны или региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
