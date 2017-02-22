---
title: "Класс locale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocale/std::locale"
  - "std::locale"
  - "std.locale"
  - "locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale - класс"
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# Класс locale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс, описывающий объект языкового стандарта, инкапсулирующий данные по соответствующей культуре в качестве набора аспектов, которые собирательно определяют ту или иную локализованную среду.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>Примечания  
 Аспект является указателем на объект класса, производного от класса [аспекта](#facet_class) обладает открытым объектом в форме:  
  
```  
static locale::id id;  
```  
  
 Можно задать открытый набор данных аспектов. Можно также создать объект языкового стандарта, назначающий произвольное количество аспектов.  
  
 Предопределенные группы данных аспектов представляют [категории языкового стандарта](#locale__category) традиционно управляет в стандартной библиотеке C функция `setlocale`.  
  
 Категория collate (LC_COLLATE) включает аспекты:  
  
```  
collate<char>  
collate<wchar_t>  
```  
  
 Категория ctype (LC_CTYPE) включает аспекты:  
  
```  
ctype<char>  
ctype<wchar_t>  
codecvt<char, char, mbstate_t>  
codecvt<wchar_t, char, mbstate_t>  
codecvt<char16_t, char, mbstate_t>  
codecvt<char32_t, char, mbstate_t>  
```  
  
 Категория monetary (LC_MONETARY) включает аспекты:  
  
```  
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
  
```  
num_get<char, istreambuf_iterator<char>>  
num_get<wchar_t, istreambuf_iterator<wchar_t>>  
num_put<char, ostreambuf_iterator<char>>  
num_put<wchar_t, ostreambuf_iterator<wchar_t>>  
numpunct<char>  
numpunct<wchar_t>  
```  
  
 Категория time (LC_TIME) включает аспекты:  
  
```  
time_get<char, istreambuf_iterator<char>>  
time_get<wchar_t, istreambuf_iterator<wchar_t>>  
time_put<char, ostreambuf_iterator<char>>  
time_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 Категория messages (LC_MESSAGES) включает аспекты:  
  
```  
messages<char>  
messages<wchar_t>  
```  
  
 (Последняя категория необходима Posix для, но не стандартной библиотеке C).  
  
 Некоторые из этих предопределенных аспектов используются классами iostreams для управления преобразованием числовых значений в текстовые последовательности и наоборот.  
  
 Объект класса Locale также сохраняет имя языкового стандарта в качестве объекта класса [строки](../Topic/%3Cstring%3E%20typedefs.md#string). Использование недопустимого имени языкового стандарта для создания аспекта языкового стандарта или объекта языкового стандарта генерирует объект класса [runtime_error](../Topic/runtime_error%20Class.md). Сохраненное имя языкового стандарта — `"*"`, если объект языкового стандарта не может быть уверен в том, что локальный стандарт языка C точно соответствует представленному данным объектом. В противном случае, можно установить соответствующий языковой стандарт в стандартной библиотеке C для объекта языкового стандарта `_Loc`, путем вызова `setlocale`(LC_ALL `,` `_Loc`. [имя](#locale__name)`().c_str()`).  
  
 В данном случае можно также вызвать статическую функцию-член:  
  
```  
static locale empty();
```  
  
 создать объект языкового стандарта без аспектов. Это также прозрачный языковой стандарт; Если функции шаблона [has_facet](../Topic/%3Clocale%3E%20functions.md#has_facet) и [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) не удается найти запрошенный аспект в прозрачном языковом стандарте, они сначала обращаются глобальной национальной настройки и затем, если таковой является прозрачным, классический языковой стандарт. Таким образом, можно написать:  
  
```  
cout.imbue(locale::empty());
```  
  
 Последующие вставки в [cout](../Topic/%3Ciostream%3E%20functions.md#cout) опосредованы текущее состояние глобального языкового стандарта. Можно даже написать:  
  
```  
locale loc(locale::empty(),
    locale::classic(),  
    locale::numeric);

cout.imbue(loc);
```   
  
 Числовые правила форматирования для последующих вставок в `cout` остаются такими же, как в языковом стандарте C, даже если глобальный языковой стандарт предоставляет другие правила вставки дат и денежных сумм.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[языковой стандарт](#locale__locale)|Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[категории](#locale__category)|Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[Объединение](#locale__combine)|Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.|  
|[Имя](#locale__name)|Возвращает имя сохраненного языкового стандарта.|  
  
### <a name="static-functions"></a>Статические функции  
  
|||  
|-|-|  
|[Классический](#locale__classic)|Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.|  
|[глобальные](#locale__global)|Сброс языкового стандарта программы по умолчанию.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор! =](#locale__operator_neq)|Проверка двух языковых стандартов на неравенство.|  
|[оператор)](#locale__operator__)|Сравнивает два объекта `basic_string`.|  
|[оператор ==](#locale__operator_eq_eq)|Проверка двух языковых стандартов на равенство.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[аспект](#facet_class)|Класс, используемый как базовый класс для всех аспектов языкового стандарта.|  
|[Идентификатор](#id_class)|Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
##  <a name="a-namelocalecategorya-localecategory"></a><a name="locale__category"></a>  locale::category  
 Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.  
  
```  
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
 Тип является синонимом `int` тип, который может представлять группу различающиеся элементы Битовая маска введите локальный класс языковой стандарт или может использоваться для представления любого из соответствующей категории языкового стандарта C. Элементами являются:  
  
- **разбор по копиям**, что соответствует категории C LC_COLLATE  
  
- **CType**, что соответствует категории C LC_CTYPE  
  
- **денежные**, что соответствует категории C LC_MONETARY  
  
- **числовые**, что соответствует категории C LC_NUMERIC  
  
- **время**, что соответствует категории C LC_TIME  
  
- **сообщения**, что соответствует категории Posix LC_MESSAGES  
  
 Кроме того два полезных доступны следующие значения:  
  
- **Нет**, что соответствует ни одна из категорий C  
  
- **все**, что соответствует объединение всех категорий LC_ALL C  
  
 Произвольные группы категорий можно представить с помощью `OR` эти константы, как и в **денежных** &#124; **время**.  
  
##  <a name="a-namelocaleclassica-localeclassic"></a><a name="locale__classic"></a>  locale::Classic  
 Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на языковом стандарте C.  
  
### <a name="remarks"></a>Примечания  
 Классический языковой стандарт C является США. ASCII английский языковой стандарт в стандартной библиотеке C, которая используется в программах, которые не являются международного неявно.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namelocalecombinea-localecombine"></a><a name="locale__combine"></a>  locale::Combine  
 Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.  
  
```  
template <class Facet>  
locale combine(const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Loc`  
 Языковой стандарт, содержащий аспект, который должен быть вставлен в целевой языковой стандарт.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член возвращает объект языкового стандарта, заменяет или добавляет **\*это** аспекта `Facet` в `_Loc`.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namefacetclassa-facet-class"></a><a name="facet_class"></a>  Класс Facet  
 Класс, используемый как базовый класс для всех аспектов языкового стандарта.  
  
Класс аспекта {защищенных: явные аспекта (size_t _Refs = 0); виртуального ~ facet(); private: facet(const facet&) или / не определен оператор void =(const facet&) или или не определен};  
  
### <a name="remarks"></a>Примечания  
 Обратите внимание, невозможно копировать или присвоить объект класса аспекта. Можно создавать и удалять объекты, производные от класса `locale::facet` но не объекты правильного базового класса. Как правило, создайте объект `_Myfac` производными аспект при создании языкового стандарта, как и в **localeloc**( `locale::classic`(), **новые**`_Myfac`);  
  
 В таких случаях конструктор для аспекта базовый класс должен иметь нулевое значение `_Refs` аргумент. Когда объект больше не нужен, он удаляется. Таким образом, необходимо указать ненулевое значение _ *Refs* аргумента только в тех редких случаях, где нести ответственность за время существования объекта.  
  
##  <a name="a-namelocaleglobala-localeglobal"></a><a name="locale__global"></a>  locale::Global  
 Сбрасывает языковой стандарт по умолчанию для программы. Это влияет на глобальный языковой стандарт C и C++.  
  
```  
static locale global(const locale& _Loc);
```  
  
### <a name="parameters"></a>Параметры  
 `_Loc`  
 Язык, который будет использоваться программой в качестве языка по умолчанию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущие языковой стандарт сброса языковой стандарт по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 При запуске программы глобального языкового стандарта совпадает классический языковой стандарт.  `global()` Вызовы функций `setlocale( LC_ALL, loc.name. c_str())` установить соответствующий языковой стандарт в стандартной библиотеки c..  
  
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
  
##  <a name="a-nameidclassa-id-class"></a><a name="id_class"></a>  Идентификатор класса  
 Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.  
  
Идентификатор класса {защищенных: id(); private: id(const id&) / / не определен оператор void =(const id&) или или не определен};  
  
### <a name="remarks"></a>Примечания  
 Член класса описывает объект статический элемент, необходимый для каждого аспекта уникальный языкового стандарта. Обратите внимание, что невозможно копировать или присвоить объект класса **идентификатор**.  
  
##  <a name="a-namelocalelocalea-localelocale"></a><a name="locale__locale"></a>  locale::Locale  
 Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта.  
  
```  
locale();

explicit locale(
    const char* _Locname,  
    category _Cat = all);

explicit locale(
    const string& _Locname);

locale(
    const locale& _Loc);

locale(
    const locale& _Loc,   
    const locale& _Other,  
    category _Cat);

locale(
    const locale& _Loc,   
    const char* _Locname,  
    category _Cat);

template <class Facet>  
locale(
 const locale& _Loc,   
    const Facet* _Fac);
```  
  
### <a name="parameters"></a>Параметры  
 `_Locname`  
 Имя языкового стандарта.  
  
 `_Loc`  
 Языковой стандарт, который будет копироваться в создании нового языкового стандарта.  
  
 `_Other`  
 Языковой стандарт, в котором можно выбрать категорию.  
  
 `_Cat`  
 Категория, будут заменены в сконструированный языкового стандарта.  
  
 `_Fac`  
 Аспект, который должен быть замещен в сконструированный языковой стандарт.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует объект в соответствии глобальный языковой стандарт. Второй и третий конструкторы выполняют инициализацию все категории языкового стандарта, поведение согласуется с именем языкового стандарта `_Locname`. Копировать оставшиеся конструкторы `_Loc`, за исключением указанных:  
  
 `locale(const locale& _Loc, const locale& _Other, category _Cat);`  
  
 заменяет из `_Other` эти аспекты, соответствующее категории C для какой C & `_Cat` имеет ненулевое значение.  
  
 `locale(const locale& _Loc, const char* _Locname, category _Cat);`  
  
 `locale(const locale& _Loc, const string& _Locname, category _Cat);`  
  
 заменяет из `locale(_Locname, _All)` эти аспекты, соответствующее категории C для какой C & `_Cat`имеет ненулевое значение.  
  
 `template<class Facet> locale(const locale& _Loc, Facet* _Fac);`  
  
 заменяет в (или добавляет) `_Loc` аспекта `_Fac`, если `_Fac` не является указателем null.  
  
 Если имя языкового стандарта `_Locname` является пустым указателем или недопустимо, вызывает функцию [runtime_error](../Topic/runtime_error%20Class.md).  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namelocalenamea-localename"></a><a name="locale__name"></a>  locale::Name  
 Возвращает имя сохраненного языкового стандарта.  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, задающая имя языкового стандарта.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namelocaleoperatorneqa-localeoperator"></a><a name="locale__operator_neq"></a>  locale::operator! =  
 Проверка двух языковых стандартов на неравенство.  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Один из языков в для проверки на неравенство.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, равное **true** Если языки не копии тот же языковой стандарт; **false** Если языковые стандарты являются копиями тот же языковой стандарт.  
  
### <a name="remarks"></a>Примечания  
 Языковые параметры считаются равными, если это тот же языковой стандарт, если такая копия другой, или если они имеют одинаковые имена.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namelocaleoperatora-localeoperator"></a><a name="locale__operator__"></a>  locale:: operator()  
 Сравнивает два объекта `basic_string`.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` left`  
 Левая строка.  
  
 ` right`  
 Правая строка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция-член возвращает:  
  
-   -1, если первая последовательность оказывается меньше, чем второй последовательности.  
  
-   + 1, если вторая последовательность оказывается меньше, чем первой последовательности.  
  
-   0, если последовательностей являются эквивалентными.  
  
### <a name="remarks"></a>Примечания  
 Функция-член фактически выполняется.  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) <0);
```  
  
 Таким образом можно использовать объект языкового стандарта, как объект функции.  
  
### <a name="example"></a>Пример  
  
```  
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
  
##  <a name="a-namelocaleoperatoreqeqa-localeoperator"></a><a name="locale__operator_eq_eq"></a>  locale::operator ==  
 Проверка двух языковых стандартов на равенство.  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Один из языков в для проверки на равенство.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Логическое значение, равное **true** Если языковые стандарты являются копиями тот же языковой стандарт; **false** Если языки не копии того же языкового стандарта.  
  
### <a name="remarks"></a>Примечания  
 Языковые параметры считаются равными, если это тот же языковой стандарт, если такая копия другой, или если они имеют одинаковые имена.  
  
### <a name="example"></a>Пример  
  
```  
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
 [\< языкового стандарта>](../standard-library/locale.md)   
 [Кодовые страницы](../c-runtime-library/code-pages.md)   
 [Имени языкового стандарта, языков и стран и регионов](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

