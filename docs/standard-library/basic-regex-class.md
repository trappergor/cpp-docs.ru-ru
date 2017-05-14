---
title: "Класс basic_regex | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_regex
- regex/std::basic_regex
dev_langs:
- C++
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f7b9afbe09fe010596a40f37eba9b0679a38268c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="basicregex-class"></a>Класс basic_regex
Создание оболочки для регулярного выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class basic_regex {  
   public:  
   basic_regex();
   explicit basic_regex(const Elem *ptr,  
   flag_type flags = ECMAScript);
   basic_regex(const Elem *ptr, size_type len,  
   flag_type flags = ECMAScript);
   basic_regex(const basic_regex& right);
   template <class STtraits, class STalloc>  
   explicit basic_regex(const basic_string<Elem, STtraits, STalloc>& str,  
   flag_type flags = ECMAScript);
   template <class InIt>  
   explicit basic_regex(InIt first, InIt last,  
   flag_type flags = ECMAScript);
   basic_regex& operator=(const basic_regex& right);
   basic_regex& operator=(const Elem *ptr);
   template <class STtraits, class STalloc>  
   basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
   basic_regex& assign(const basic_regex& right);
   basic_regex& assign(const Elem *ptr,  
   flag_type flags = ECMAScript);
   basic_regex& assign(const Elem *ptr, size_type len,  
   flag_type flags = ECMAScript);
   template <class STtraits, class STalloc>  
   basic_regex& assign(const basic_string<Elem, STtraits, STalloc>& str,  
   flag_type flags = ECMAScript);
   template <class InIt>  
   basic_regex& assign(InIt first, InIt last,  
   flag_type flags = ECMAScript);
   locale_type imbue(locale_type loc);
   locale_type getloc() const;
   void swap(basic_regex& other) throw();
   unsigned mark_count() const;
   flag_type flags() const;
   typedef Elem value_type;  
   typedef regex_constants::syntax_option_type flag_type;  
   typedef typename RXtraits::locale_type locale_type;  
   static const flag_type icase = regex_constants::icase;  
   static const flag_type nosubs = regex_constants::nosubs;  
   static const flag_type optimize = regex_constants::optimize;  
   static const flag_type collate = regex_constants::collate;  
   static const flag_type ECMAScript = regex_constants::ECMAScript;  
   static const flag_type basic = regex_constants::basic;  
   static const flag_type extended = regex_constants::extended;  
   static const flag_type awk = regex_constants::awk;  
   static const flag_type grep = regex_constants::grep;  
   static const flag_type egrep = regex_constants::egrep;  
   private:  
   RXtraits traits;    // exposition only  
   };  
   ```   
  
#### <a name="parameters"></a>Параметры  
 `Elem`  
 Тип элементов для обеспечения соответствия.  
  
 `RXtraits`  
 Класс характеристик для элементов.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает объект, содержащий регулярное выражение. Объекты данного класса шаблона может быть передан функции шаблона [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search), и [regex_replace](../standard-library/regex-functions.md#regex_replace), наряду с подходящими аргументами текстовой строки, для поиска текста, который соответствует регулярному выражению. Существует две специализации данного класса шаблона: с определениями типов [regex](../standard-library/regex-typedefs.md#regex) для элементов типа `char` и [wregex](../standard-library/regex-typedefs.md#wregex) для элементов типа `wchar_t`.  
  
 Аргумент шаблона `RXtraits` описывает различные важные свойства синтаксиса регулярных выражений, поддерживаемых классом шаблона. Класс, определяющий эти характеристики регулярного выражения, должен обладать таким же внешним интерфейсом, как и объект класса шаблона [regex_traits](../standard-library/regex-traits-class.md).  
  
 Некоторые функции принимают последовательность операндов, определяющую регулярное выражение. Такую последовательность операндов можно задать несколькими способами:  
  
 `ptr` -- последовательность, завершенная символом null (например, строка C для `Elem` типа `char`), начиная с `ptr` (это должен быть пустой указатель), где завершаемый элемент является значением `value_type()` и не входит в последовательность операндов  
  
 `ptr`, `count` -- последовательность элементов `count`, начиная с `ptr` (это должен быть не пустой указатель)  
  
 `str` -- последовательность, заданная объектом `basic_string` `str`  
  
 `first`, `last` -- последовательность элементов, разделенная итераторами `first` и `last`, в диапазоне `[first, last)`  
  
 `right` -- объект `basic_regex` `right`  
  
 Эти функции-члены также принимают аргумент `flags`, который определяет различные параметры для интерпретации регулярных выражений в дополнение к параметрам, описанным типом `RXtraits`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<regex>  
  
 **Пространство имен:** std  
  
##  <a name="assign"></a>  basic_regex::assign  
 Присваивает значение объекту регулярного выражения.  
  
```  
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,  
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,   
    size_type len,  
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,  
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>  
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,  
    flag_type flags = ECMAScript);

template <class InIt>  
basic_regex& assign(
    InIt first, InIt last,  
    flag_type flags = ECMAScript);
```  
  
### <a name="parameters"></a>Параметры  
 `STtraits`  
 Класс признаков для источника строки.  
  
 `STalloc`  
 Класс распределителя для источника строки.  
  
 `InIt`  
 Тип итератора ввода для источника диапазона.  
  
 `right`  
 Копируемый источник регулярного выражения.  
  
 `ptr`  
 Копируемый указатель на начало последовательности.  
  
 `flags`  
 Добавляемые при копировании флаги вариантов синтаксиса.  
  
 `len/TD>`  
 Копируемый конец последовательности.  
  
 `str`  
 Копируемая строка.  
  
 `first`  
 Копируемое начало последовательности.  
  
 `last`  
 Копируемый конец последовательности.  
  
 `IList`  
 Копируемый initializer_list.  
  
### <a name="remarks"></a>Примечания  
 Каждая функция-член заменяет регулярное выражение, хранящееся в `*this`, на регулярное выражение, описываемое последовательностью операндов, а затем возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_assign.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
using namespace std;  
  
int main()  
{  
    regex::value_type elem = 'x';  
    regex::flag_type flag = regex::grep;  
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;  
  
    // constructors   
    regex rx0;  
    cout << "match(\"abc\", \"\") == " << boolalpha  
        << regex_match("abc", rx0) << endl;  
  
    regex rx1("abcd", regex::ECMAScript);  
    cout << "match(\"abc\", \"abcd\") == " << boolalpha  
        << regex_match("abc", rx1) << endl;  
  
    regex rx2("abcd", 3);  
    cout << "match(\"abc\", \"abc\") == " << boolalpha  
        << regex_match("abc", rx2) << endl;  
  
    regex rx3(rx2);  
    cout << "match(\"abc\", \"abc\") == " << boolalpha  
        << regex_match("abc", rx3) << endl;  
  
    string str("abcd");  
    regex rx4(str);  
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha  
        << regex_match("abc", rx4) << endl;  
  
    regex rx5(str.begin(), str.end() - 1);  
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha  
        << regex_match("abc", rx5) << endl;  
    cout << endl;  
  
    // assignments   
    rx0 = "abc";  
    rx0 = rx1;  
    rx0 = str;  
  
    rx0.assign("abcd", regex::ECMAScript);  
    rx0.assign("abcd", 3);  
    rx0.assign(rx1);  
    rx0.assign(str);  
    rx0.assign(str.begin(), str.end() - 1);  
  
    rx0.swap(rx1);  
  
    // mark_count   
    cout << "\"abc\" mark_count == "  
        << regex("abc").mark_count() << endl;  
    cout << "\"(abc)\" mark_count == "  
        << regex("(abc)").mark_count() << endl;  
  
    // locales   
    regex::locale_type loc = rx0.imbue(locale());  
    cout << "getloc == imbued == " << boolalpha  
        << (loc == rx0.getloc()) << endl;  
  
    // initializer_list  
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);  
    cout << "match(\"abc\") == " << boolalpha  
        << regex_match("abc", rx6);  
    cout << endl;   
}  
  
```  
  
```Output  
match("abc", "") == falsematch("abc", "abcd") == falsematch("abc", "abc") == truematch("abc", "abc") == truematch(string("abcd"), "abc") == falsematch(string("abc"), "abc") == true"abc" mark_count == 0"(abc)" mark_count == 1getloc == imbued == truematch("abc") == true  
```  
  
##  <a name="basic_regex"></a>  basic_regex::basic_regex  
 Конструирует объект регулярного выражения.  
  
```  
basic_regex();

explicit basic_regex(
    const Elem* ptr,  
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,   
    size_type len,  
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,  
    flag_type flags);

template <class STtraits, class STalloc>  
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,  
    flag_type flags);

template <class InIt>  
explicit basic_regex(
    InIt first,   
    InIt last,  
    flag_type flags);
```  
  
### <a name="parameters"></a>Параметры  
 `STtraits`  
 Класс признаков для источника строки.  
  
 `STalloc`  
 Класс распределителя для источника строки.  
  
 `InIt`  
 Тип итератора ввода для источника диапазона.  
  
 `right`  
 Копируемый источник регулярного выражения.  
  
 `ptr`  
 Копируемый указатель на начало последовательности.  
  
 `flags`  
 Добавляемые при копировании флаги вариантов синтаксиса.  
  
 `len/TD>`  
 Копируемый конец последовательности.  
  
 `str`  
 Копируемая строка.  
  
 `first`  
 Копируемое начало последовательности.  
  
 `last`  
 Копируемый конец последовательности.  
  
 `IList`  
 Копируемый initializer_list.  
  
### <a name="remarks"></a>Примечания  
 Все последовательности хранят объект типа `RXtraits`, сконструированный по умолчанию.  
  
 Первый конструктор создает пустой объект `basic_regex`. Другие конструкторы создают объект `basic_regex`, который содержит регулярное выражение, описанное последовательностью операндов.  
  
 Пустой `basic_regex` объект не соответствует любой последовательности символов, при передаче в [regex_match](../standard-library/regex-functions.md#regex_match), [regex_search](../standard-library/regex-functions.md#regex_search), или [regex_replace](../standard-library/regex-functions.md#regex_replace).  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
using namespace std;  
  
int main()  
{  
    regex::value_type elem = 'x';  
    regex::flag_type flag = regex::grep;  
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;  
  
    // constructors   
    regex rx0;  
    cout << "match(\"abc\", \"\") == " << boolalpha  
        << regex_match("abc", rx0) << endl;  
  
    regex rx1("abcd", regex::ECMAScript);  
    cout << "match(\"abc\", \"abcd\") == " << boolalpha  
        << regex_match("abc", rx1) << endl;  
  
    regex rx2("abcd", 3);  
    cout << "match(\"abc\", \"abc\") == " << boolalpha  
        << regex_match("abc", rx2) << endl;  
  
    regex rx3(rx2);  
    cout << "match(\"abc\", \"abc\") == " << boolalpha  
        << regex_match("abc", rx3) << endl;  
  
    string str("abcd");  
    regex rx4(str);  
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha  
        << regex_match("abc", rx4) << endl;  
  
    regex rx5(str.begin(), str.end() - 1);  
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha  
        << regex_match("abc", rx5) << endl;  
    cout << endl;  
  
    // assignments   
    rx0 = "abc";  
    rx0 = rx1;  
    rx0 = str;  
  
    rx0.assign("abcd", regex::ECMAScript);  
    rx0.assign("abcd", 3);  
    rx0.assign(rx1);  
    rx0.assign(str);  
    rx0.assign(str.begin(), str.end() - 1);  
  
    rx0.swap(rx1);  
  
    // mark_count   
    cout << "\"abc\" mark_count == "  
        << regex("abc").mark_count() << endl;  
    cout << "\"(abc)\" mark_count == "  
        << regex("(abc)").mark_count() << endl;  
  
    // locales   
    regex::locale_type loc = rx0.imbue(locale());  
    cout << "getloc == imbued == " << boolalpha  
        << (loc == rx0.getloc()) << endl;  
  
    // initializer_list  
    regex rx6{ { 'a', 'b', 'c' } };  
    cout << "match(\"abc\", \"abc\") == " << boolalpha  
        << regex_match("abc", rx6);  
    cout << endl;  
}  
  
```  
  
```Output  
match("abc", "") == falsematch("abc", "abcd") == falsematch("abc", "abc") == truematch("abc", "abc") == truematch(string("abcd"), "abc") == falsematch(string("abc"), "abc") == true"abc" mark_count == 0"(abc)" mark_count == 1getloc == imbued == truematch("abc", "abc") == true  
```  
  
##  <a name="flag_type"></a>  basic_regex::flag_type  
 Тип флагов параметров синтаксиса.  
  
```  
typedef regex_constants::syntax_option_type flag_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_flag_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="flags"></a>  basic_regex::flags  
 Возвращает флаги параметров синтаксиса.  
  
```  
flag_type flags() const;
```  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член возвращает значение аргумента `flag_type`, переданного в последний вызов одной из функций-членов [basic_regex::assign](#assign), или, если вызовы не выполнялись, возвращает значение, переданное в конструктор.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_flags.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="getloc"></a>  basic_regex::getloc  
 Возвращает сохраненный объект языкового стандарта.  
  
```  
locale_type getloc() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `traits.`[regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_getloc.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="imbue"></a>  basic_regex::imbue  
 Изменяет сохраненный объект языкового стандарта.  
  
```  
locale_type imbue(locale_type loc);
```  
  
### <a name="parameters"></a>Параметры  
 `loc`  
 Объект языкового стандарта, который необходимо сохранить.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член очищает `*this` и возвращает `traits.`[regex_traits::imbue](../standard-library/regex-traits-class.md#imbue)`(loc)`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_imbue.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="locale_type"></a>  basic_regex::locale_type  
 Тип сохраненного объекта языкового стандарта.  
  
```  
typedef typename RXtraits::locale_type locale_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type).  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_locale_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="mark_count"></a>  basic_regex::mark_count  
 Возвращает число сопоставленных частей выражения.  
  
```  
unsigned mark_count() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число групп записи в регулярном выражении.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_mark_count.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="op_eq"></a>  basic_regex::operator=  
 Присваивает значение объекту регулярного выражения.  
  
```  
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>  
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```  
  
### <a name="parameters"></a>Параметры  
 `STtraits`  
 Класс признаков для источника строки.  
  
 `STalloc`  
 Класс распределителя для источника строки.  
  
 `right`  
 Копируемый источник регулярного выражения.  
  
 `str`  
 Копируемая строка.  
  
### <a name="remarks"></a>Примечания  
 Каждый оператор заменяет регулярное выражение, хранящееся в `*this` , на регулярное выражение, описываемое последовательностью операндов, а затем возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_operator_as.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="swap"></a>  basic_regex::swap  
 Меняет местами два объекта регулярного выражения.  
  
```  
void swap(basic_regex& right) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект регулярного выражения для замены.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами регулярные выражения между `*this` и `right`. Она делает это в константном времени и не создает исключений.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_swap.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
##  <a name="value_type"></a>  basic_regex::value_type  
 Тип элемента.  
  
```  
typedef Elem value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра шаблона `Elem`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__basic_regex_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex::value_type elem = 'x';   
    std::regex::flag_type flag = std::regex::grep;   
  
    elem = elem;  // to quiet "unused" warnings   
    flag = flag;   
  
// constructors   
    std::regex rx0;   
    std::cout << "match(\"abc\", \"\") == " << std::boolalpha   
        << regex_match("abc", rx0) << std::endl;   
  
    std::regex rx1("abcd", std::regex::ECMAScript);   
    std::cout << "match(\"abc\", \"abcd\") == " << std::boolalpha   
        << regex_match("abc", rx1) << std::endl;   
  
    std::regex rx2("abcd", 3);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx2) << std::endl;   
  
    std::regex rx3(rx2);   
    std::cout << "match(\"abc\", \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx3) << std::endl;   
  
    std::string str("abcd");   
    std::regex rx4(str);   
    std::cout << "match(string(\"abcd\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx4) << std::endl;   
  
    std::regex rx5(str.begin(), str.end() - 1);   
    std::cout << "match(string(\"abc\"), \"abc\") == " << std::boolalpha   
        << regex_match("abc", rx5) << std::endl;   
    std::cout << std::endl;   
  
// assignments   
    rx0 = "abc";   
    rx0 = rx1;   
    rx0 = str;   
  
    rx0.assign("abcd", std::regex::ECMAScript);   
    rx0.assign("abcd", 3);   
    rx0.assign(rx1);   
    rx0.assign(str);   
    rx0.assign(str.begin(), str.end() - 1);   
  
    rx0.swap(rx1);   
  
// mark_count   
    std::cout << "\"abc\" mark_count == "   
        << std::regex("abc").mark_count() << std::endl;   
    std::cout << "\"(abc)\" mark_count == "   
        << std::regex("(abc)").mark_count() << std::endl;   
  
// locales   
    std::regex::locale_type loc = rx0.imbue(std::locale());   
    std::cout << "getloc == imbued == " << std::boolalpha   
        << (loc == rx0.getloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
match("abc", "") == false  
match("abc", "abcd") == false  
match("abc", "abc") == true  
match("abc", "abc") == true  
match(string("abcd"), "abc") == false  
match(string("abc"), "abc") == true  
  
"abc" mark_count == 0  
"(abc)" mark_count == 1  
getloc == imbued == true  
```  
  
## <a name="see-also"></a>См. также  
 [\<regex>](../standard-library/regex.md)   
 [regex_match](../standard-library/regex-functions.md#regex_match)   
 [regex_search](../standard-library/regex-functions.md#regex_search)   
 [regex_replace](../standard-library/regex-functions.md#regex_replace)   
 [regex](../standard-library/regex-typedefs.md#regex)   
 [wregex](../standard-library/regex-typedefs.md#wregex)   
 [Класс regex_traits](../standard-library/regex-traits-class.md)


