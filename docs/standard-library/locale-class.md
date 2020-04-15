---
title: Класс locale
ms.date: 03/19/2019
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
ms.openlocfilehash: 2581c5cdacc9e542f5d911860128dcf5526621ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367316"
---
# <a name="locale-class"></a>Класс locale

Класс, описывающий объект языкового стандарта, инкапсулирующий данные по соответствующей культуре в качестве набора аспектов, которые собирательно определяют ту или иную локализованную среду.

## <a name="syntax"></a>Синтаксис

```cpp
class locale;
```

## <a name="remarks"></a>Remarks

Аспект — это указатель на объект класса, выведенного производным от класса [facet](#facet_class), который обладает общим объектом в формате:

```cpp
static locale::id id;
```

Можно задать открытый набор данных аспектов. Можно также создать объект языкового стандарта, назначающий произвольное количество аспектов.

Предопределенные группы этих аспектов представляют [категории языкового стандарта](#category), которыми в стандартной библиотеке C традиционно управляет функция `setlocale`.

Категория `collate` (LC_COLLATE) включает в себя аспекты:

```cpp
collate<char>
collate<wchar_t>
```

Категория `ctype` (LC_CTYPE) включает в себя аспекты:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Категория `monetary` (LC_MONETARY) включает в себя аспекты:

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

Категория `numeric` (LC_NUMERIC) включает в себя аспекты:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Категория `time` (LC_TIME) включает в себя аспекты:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Категория `messages` (LC_MESSAGES) включает в себя аспекты:

```cpp
messages<char>
messages<wchar_t>
```

(Последняя категория требуется POSIX, но не C Standard.)

Некоторые из этих предопределенных аспектов `iostream` используются классами для контроля преобразования числовых значений в текстовые последовательности и из них.

Объект класса locale также сохраняет имя языкового стандарта в качестве объекта класса [string](../standard-library/string-typedefs.md#string). Использование недопустимого имени языкового стандарта для создания аспекта языкового стандарта или объекта языкового стандарта создает объект класса [runtime_error](../standard-library/runtime-error-class.md). Сохраненное имя `"*"` локали, если объект локали не может быть уверен в том, что c-стиль соответствует точно тому, который представлен объектом. В противном случае можно создать соответствующий локаль в библиотеке `locale_object`Standard `setlocale(LC_ALL , locale_object.`C для некоторых объектов локализации, позвонив [по имени.](#name)`().c_str())`

В данном случае можно также вызвать статическую функцию-член:

```cpp
static locale empty();
```

создать объект языкового стандарта без аспектов. Это также прозрачный локализ. Если шаблон функционирует [has_facet](../standard-library/locale-functions.md#has_facet) и [use_facet](../standard-library/locale-functions.md#use_facet) не могут найти запрошенную грань в прозрачном локаль, они консультируются сначала с глобальным локалью, а затем, если это прозрачно, классическим локалью. Таким образом, вы можете написать:

```cpp
cout.imbue(locale::empty());
```

Последующие вставки [`cout`](../standard-library/iostream.md#cout) опосредования со посредниками являются текущее состояние глобального локаль. Можно даже написать:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Числовые правила форматирования для последующих вставок в `cout` остаются такими же, как в языковом стандарте C, даже если глобальный языковой стандарт предоставляет другие правила вставки дат и денежных сумм.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[Языкового стандарта](#locale)|Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[Категории](#category)|Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Объединить](#combine)|Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.|
|[name](#name)|Возвращает имя сохраненного языкового стандарта.|

### <a name="static-functions"></a>Статические функции

|||
|-|-|
|[Классический](#classic)|Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.|
|[Глобального](#global)|Сброс языкового стандарта программы по умолчанию.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Назначает локализу.|
|[оператора!](#op_neq)|Проверка двух языковых стандартов на неравенство.|
|[оператор()](#op_call)|Сравнивает два объекта `basic_string`.|
|[оператора](#op_eq_eq)|Проверка двух языковых стандартов на равенство.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[facet](#facet_class)|Класс, используемый как базовый класс для всех аспектов языкового стандарта.|
|[`id`](#id_class)|Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="localecategory"></a><a name="category"></a>локал::категория

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

### <a name="remarks"></a>Remarks

Тип является синонимом для типа **int,** который может представлять группу отдельных элементов типа битмаски локального к месту класса или может быть использован для представления любой из соответствующих категорий C locale. Элементы:

- `collate`, соответствующие категории C LC_COLLATE

- `ctype`, соответствующие категории C LC_CTYPE

- `monetary`, соответствующие категории C LC_MONETARY

- `numeric`, соответствующие категории C LC_NUMERIC

- `time`, соответствующие категории C LC_TIME

- `messages`, соответствующие категории POSIX LC_MESSAGES

Еще два полезных значения:

- `none`, что не соответствует ни одной из категорий C

- `all`, соответствующий союзу C всех категорий LC_ALL

Вы можете представлять произвольную группу категорий, используя `OR` с этими константами, как и в `monetary` &#124; `time`.

## <a name="localeclassic"></a><a name="classic"></a>локал::классический

Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на языковой стандарт C.

### <a name="remarks"></a>Remarks

Классическим C locale является английский язык ASCII в библиотеке Standard C. Это локал, который используется неявно в программах, которые не интернационализированы.

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

## <a name="localecombine"></a><a name="combine"></a>локал::комбинат

Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.

```cpp
template <class Facet>
locale combine(const locale& source_locale) const;
```

### <a name="parameters"></a>Параметры

*source_locale*\
Языковой стандарт, содержащий аспект для вставки в целевой языковой стандарт.

### <a name="return-value"></a>Возвращаемое значение

Функция участника возвращает объект локали, который заменяет или `Facet` добавляет к ** \*этому** грань, перечисленные в *source_locale.*

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

## <a name="facet-class"></a><a name="facet_class"></a>класс граней

Класс, используемый как базовый класс для всех аспектов языкового стандарта.

```cpp
class facet {
protected:
    explicit facet(size_t references = 0);
    virtual ~facet();
private:
    facet(const facet&) // not defined
    void operator=(const facet&) // not defined
};
```

### <a name="remarks"></a>Remarks

Вы не можете скопировать или назначить объект класса. `facet` Можно создавать и удалять объекты, производные от класса `locale::facet`, но не объекты правильного базового класса. Как правило, вы `_Myfac` строите `facet` объект, `locale`полученный от построения, как в`locale loc(locale::classic(), new _Myfac);`

В таких случаях конструктор для базового класса `facet` должен иметь аргумент нулевой *ссылки.* Когда объект больше не нужен, он удаляется, поэтому вы поставляюте аргумент *ненулевой ссылки* только в тех редких случаях, когда вы берете на себя ответственность за срок службы объекта.

## <a name="localeglobal"></a><a name="global"></a>локал:Глобальный

Сброс языкового стандарта по умолчанию для программы. Этот вызов влияет на глобальную локаль как для C, так и для C.

```cpp
static locale global(const locale& new_default_locale);
```

### <a name="parameters"></a>Параметры

*new_default_locale*\
Языковой стандарт, который будет использоваться программой по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Языковой стандарт до сброса языкового стандарта по умолчанию.

### <a name="remarks"></a>Remarks

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

## <a name="id-class"></a><a name="id_class"></a>id Класс

Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.

```cpp
class id
{
   protected:    id();
   private:      id(const id&)
   void operator=(const id&)  // not defined
};
```

### <a name="remarks"></a>Remarks

Класс-член описывает статический объект-член, необходимый для каждого уникального аспекта языкового стандарта. Вы не можете скопировать или назначить объект класса. `id`

## <a name="localelocale"></a><a name="locale"></a>локал:местное

Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта. Также включает в себя деструктор.

```cpp
locale();

explicit locale(const char* locale_name, category new_category = all);
explicit locale(const string& locale_name);
locale(const locale& from_locale);
locale(const locale& from_locale, const locale& Other, category new_category);
locale(const locale& from_locale, const char* locale_name, category new_category);

template <class Facet>
locale(const locale& from_locale, const Facet* new_facet);

~locale();
```

### <a name="parameters"></a>Параметры

*locale_name*\
Имя языкового стандарта.

*from_locale*\
Языковой стандарт, который будет копироваться при создании нового языкового стандарта.

*Других*\
Языковой стандарт, из которого будет выбираться категория.

*new_category*\
Категория для замены в созданном языковом стандарте.

*new_facet*\
Аспект для замены в созданном языковом стандарте.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует объект для соответствия глобальному языковому стандарту. Второй и третий конструкторы инициализировать все категории локализовать, чтобы иметь поведение в соответствии с названием locale *locale_name.* Остальные конструкторы копируют *from_locale,* за исключением:

`locale(const locale& from_locale, const locale& Other, category new_category);`

заменяет из *Других* те аспекты, соответствующие категории C, для которых C & *new_category* является ненулевой.

`locale(const locale& from_locale, const char* locale_name, category new_category);`

`locale(const locale& from_locale, const string& locale_name, category new_category);`

заменяет `locale(locale_name, all)` из этих аспектов, соответствующих `replace_category & new_category` категории *replace_category,* для которых является ненулевой.

`template<class Facet> locale(const locale& from_locale, Facet* new_facet);`

заменяет (или добавляет) *from_locale* граней *new_facet,* если *new_facet* не является нулевой указатель.

Если имя локала *locale_name* является недействительным указателем или иным образом недействительным, функция бросает [runtime_error.](../standard-library/runtime-error-class.md)

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

## <a name="localename"></a><a name="name"></a>локал::имя

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

## <a name="localeoperator"></a><a name="op_eq"></a>локал::оператор

Назначает локализу.

```cpp
const locale& operator=(const locale& other) noexcept;
```

## <a name="localeoperator"></a><a name="op_neq"></a>локал::оператор!

Проверка двух языковых стандартов на неравенство.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Параметры

*Правильно*\
Один из языковых стандартов для проверки на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Значение Boolean, которое **верно,** если локалы не являются копиями одного и того же места. Это **неверно,** если локалы являются копиями одного и того же места.

### <a name="remarks"></a>Remarks

Два локоть равны, если они являются одним и тем же языком, если один из них является копией другого, или если они имеют одинаковые имена.

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

## <a name="localeoperator"></a><a name="op_call"></a>локал:оператор()

Сравнивает два объекта `basic_string`.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Параметры

*Левой*\
Левая строка.

*Правильно*\
Правая строка.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает:

- –1, если первая последовательность оказывается меньше, чем вторая;

- –1, если вторая последовательность оказывается меньше, чем первая.

- 0, если последовательности являются эквивалентными.

### <a name="remarks"></a>Remarks

Функция-член фактически выполняет:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Это означает, что вы можете использовать объект локализации в качестве объекта функции.

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

## <a name="localeoperator"></a><a name="op_eq_eq"></a>локал::оператор

Проверка двух языковых стандартов на равенство.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Параметры

*Правильно*\
Один из языковых стандартов для проверки на равенство.

### <a name="return-value"></a>Возвращаемое значение

Значение Boolean, которое **верно,** если локалы являются копиями одного и того же места. Это **неверно,** если локалы не являются копиями одного и того же места.

### <a name="remarks"></a>Remarks

Два локоть равны, если они являются одним и тем же языком, если один из них является копией другого, или если они имеют одинаковые имена.

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

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[Страницы кода](../c-runtime-library/code-pages.md)\
[Названия языков, языков и страновых/регионов](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
