---
title: "Класс match_results | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::match_results
dev_langs:
- C++
helpviewer_keywords:
- match_results class
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: bf915f8097d76ff7b21158302e1272e462294f05
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="matchresults-class"></a>Класс match_results
Содержит последовательность подстрок соответствия.  
  
## <a name="syntax"></a>Синтаксис  
```  
class match_results {  
   public:  
   explicit match_results(const Alloc& alloc = Alloc());
   match_results(const match_results& right);
   match_results& operator=(const match_results& right);
   difference_type position(size_type sub = 0) const;
   difference_type length(size_type sub = 0) const;
   string_type str(size_type sub = 0) const;
   const_reference operator[](size_type n) const;
   const_reference prefix() const;
   const_reference suffix() const;
   const_iterator begin() const;
   const_iterator end() const;
   template <class OutIt>  
   OutIt format(OutIt out,  
   const string_type& fmt, match_flag_type flags = format_default) const;
   string_type format(const string_type& fmt,  
   match_flag_type flags = format_default) const;
   allocator_type get_allocator() const;
   void swap(const match_results& other) throw();
   size_type size() const;
   size_type max_size() const;
   bool empty() const;
   typedef sub_match<BidIt>  
   value_type;  
   typedef const typename Alloc::const_reference const_reference;  
   typedef const_reference reference;  
   typedef T0 const_iterator;  
   typedef const_iterator iterator;  
   typedef typename iterator_traits<BidIt>::difference_type difference_type;  
   typedef typename Alloc::size_type size_type;  
   typedef Alloc allocator_type;  
   typedef typename iterator_traits<BidIt>::value_type char_type;  
   typedef basic_string<char_type> string_type;  
   };  
```  
#### <a name="parameters"></a>Параметры  
 `BidIt`  
 Тип итератора для подстрок соответствия.  
  
 `Alloc`  
 Тип распределителя для управления хранилищем.  
  
## <a name="remarks"></a>Примечания  
 Класс шаблона описывает объект, управляющий неизменяемой последовательностью элементов типа `sub_match<BidIt>` , созданной при поиске регулярного выражения. Каждый элемент указывает на часть последовательности, которая соответствует группе захвата, соответствующей этому элементу.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<regex>  
  
 **Пространство имен:** std  
  
##  <a name="allocator_type"></a>  match_results::allocator_type  
 Тип распределителя для управления хранилищем.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Определение типа является синонимом параметра шаблона `Alloc`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_allocator_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="begin"></a>  match_results::begin  
 Обозначает начало последовательности подстроки соответствия.  
  
```  
const_iterator begin() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор произвольного доступа, указывающий на первый элемент последовательности (или на место сразу за концом пустой последовательности).  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_begin.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="char_type"></a>  match_results::char_type  
 Тип элемента.  
  
```  
typedef typename iterator_traits<BidIt>::value_type char_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Определение типа является синонимом типа `iterator_traits<BidIt>::value_type`, который является типом элемента искомой последовательности символов.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_char_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="const_iterator"></a>  match_results::const_iterator  
 Тип постоянного итератора для подстрок соответствия.  
  
```  
typedef T0 const_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Определение типа описывает объект, который можно использовать в качестве постоянного итератора с произвольным доступом для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_const_iterator.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="const_reference"></a>  match_results::const_reference  
 Тип постоянной ссылки на элемент.  
  
```  
typedef const typename Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Определение типа описывает объект, который можно использовать в качестве постоянной ссылки на элемент управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_const_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="difference_type"></a>  match_results::difference_type  
 Тип разницы итератора.  
  
```  
typedef typename iterator_traits<BidIt>::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Определение типа является синонимом типа `iterator_traits<BidIt>::difference_type`; оно описывает объект, который может представлять разницу между любыми двумя итераторами, указывающими на элементы управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_difference_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="empty"></a>  match_results::empty  
 Проверяет отсутствие подстрок соответствия.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение true, только если не удалось найти регулярное выражение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_empty.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="end"></a>  match_results::end  
 Обозначает конец последовательности частичного соответствия.  
  
```  
const_iterator end() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор, указывающий на место сразу за концом последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_end.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="format"></a>  match_results::format  
 Форматирует подстроки соответствия.  
  
```  
template <class OutIt>  
OutIt format(OutIt out,  
    const string_type& fmt, match_flag_type flags = format_default) const;

 
string_type format(const string_type& fmt, match_flag_type flags = format_default) const;
```  
  
### <a name="parameters"></a>Параметры  
 `OutIt`  
 Тип итератора вывода.  
  
 `out`  
 Поток вывода для записи.  
  
 `fmt`  
 Строка формата.  
  
 `flags`  
 Флаги формата.  
  
### <a name="remarks"></a>Примечания  
 Каждая функция-член генерирует форматированный текст под управлением формата `fmt`. Первая функция-член записывает форматированный текст в последовательность, заданную ее аргументом `out` и возвращает `out`. Вторая функция-член возвращает объект строки, содержащий копию форматированного текста.  
  
 Чтобы создать форматированный текст, литеральный текст в строке формата, как правило, копируется в целевую последовательность. Каждая escape-последовательность в строке формата заменяется текстом, который она представляет. Сведениями о копировании и замене управляют флаги формата, передаваемые функции.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_format.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="get_allocator"></a>  match_results::get_allocator  
 Возвращает сохраненный распределитель.  
  
```  
allocator_type get_allocator() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает копию объекта распределителя, используемого `*this` для распределения его объектов `sub_match`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_get_allocator.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="iterator"></a>  match_results::iterator  
 Тип итератора для подстрок соответствия.  
  
```  
typedef const_iterator iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип описывает объект, который можно использовать в качестве итератора с произвольным доступом для управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_iterator.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="length"></a>  match_results::length  
 Возвращает длину подстроки соответствия.  
  
```  
difference_type length(size_type sub = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `sub`  
 Индекс подстроки соответствия.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение `(*this)[sub].length()`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_length.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="match_results"></a>  match_results::match_results  
 Создает объект.  
  
```  
explicit match_results(const Alloc& alloc = Alloc());

match_results(const match_results& right);
```  
  
### <a name="parameters"></a>Параметры  
 `alloc`  
 Объект распределителя для сохранения.  
  
 `right`  
 Копируемый объект match_results.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект `match_results`, который не содержит подстрок совпадения. Второй конструктор создает объект `match_results`, который является копией `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="max_size"></a>  match_results::max_size  
 Получает максимальное число подстрок соответствия.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает длину самой длинной последовательности, которой объект может управлять.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_max_size.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="op_eq"></a>  match_results::operator=  
 Копирование объекта match_results.  
  
```  
match_results& operator=(const match_results& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Копируемый объект match_results.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член заменяет последовательность, управляемую `*this`, копией последовательности, управляемой `right`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_operator_as.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="op_at"></a>  match_results::operator[]  
 Доступ к подчиненному объекту.  
  
```  
const_reference operator[](size_type n) const;
```  
  
### <a name="parameters"></a>Параметры  
 `n`  
 Индекс подстроки совпадения.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на элемент `n` управляемой последовательности или ссылку на пустой объект `sub_match` , если `size() <= n` , или если группа записи `n` не была частью соответствия.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_operator_br.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="position"></a>  match_results::position  
 Получает начальное смещение подгруппы.  
  
```  
difference_type position(size_type sub = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `sub`  
 Индекс подстроки совпадения.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `std::distance(prefix().first, (*this)[sub].first)`, то есть расстояние от первого символа в целевой последовательности до первого символа в подстроке соответствия, указанной элементом `n` управляемой последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_position.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="prefix"></a>  match_results::prefix  
 Получает последовательность перед первой подстрокой соответствия.  
  
```  
const_reference prefix() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на объект типа `sub_match<BidIt>` , указывающий на последовательность символов, которая начинается с начала целевой последовательности и заканчивается в `(*this)[0].first`, то есть он указывает на текст, который предшествует сопоставленной части последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_prefix.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="reference"></a>  match_results::reference  
 Тип ссылки на элемент.  
  
```  
typedef const_reference reference;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для типа `const_reference`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_reference.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="size"></a>  match_results::size  
 Подсчитывает количество подстрок соответствия.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает число, которое на единицу больше, чем количество групп записи в регулярном выражении, использовавшемся для поиска, или значение 0, если поиск не выполнялся.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_size.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="size_type"></a>  match_results::size_type  
 Тип числа подстрок соответствия.  
  
```  
typedef typename Alloc::size_type size_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для типа `Alloc::size_type`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_size_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="str"></a>  match_results::str  
 Возвращает подстроку совпадения.  
  
```  
string_type str(size_type sub = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `sub`  
 Индекс подстроки совпадения.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение `string_type((*this)[sub])`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_str.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="string_type"></a>  match_results::string_type  
 Тип строки.  
  
```  
typedef basic_string<char_type> string_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для типа `basic_string<char_type>`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_string_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="suffix"></a>  match_results::suffix  
 Получает последовательность после последней подстроки соответствия.  
  
```  
const_reference suffix() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает ссылку на объект типа `sub_match<BidIt>` , указывающий на последовательность символов, которая начинается с `(*this)[size() - 1].second` и заканчивается в конце целевой последовательности, то есть он указывает на текст, который следует за сопоставленной частью последовательности.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_suffix.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="swap"></a>  match_results::swap  
 Меняет местами два объекта match_results.  
  
```  
void swap(const match_results& right) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект match_results для замены.  
  
### <a name="remarks"></a>Примечания  
 Функция-член меняет местами содержимое объектов `*this` и `right` в константном времени и не создает исключение.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_swap.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
##  <a name="value_type"></a>  match_results::value_type  
 Тип подстроки соответствия.  
  
```  
typedef sub_match<BidIt> value_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Определение типа является синонимом для типа `sub_match<BidIt>`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__match_results_value_type.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex rx("c(a*)|(b)");   
    std::cmatch mr;   
  
    std::regex_search("xcaaay", mr, rx);   
  
    std::cout << "prefix: matched == " << std::boolalpha   
        << mr.prefix().matched   
        << ", value == " << mr.prefix() << std::endl;   
    std::cout << "whole match: " << mr.length() << " chars, value == "   
        << mr.str() << std::endl;   
    std::cout << "suffix: matched == " << std::boolalpha   
        << mr.suffix().matched   
        << ", value == " << mr.suffix() << std::endl;   
    std::cout << std::endl;   
  
    std::string fmt("\"c(a*)|(b)\" matched \"$0\"\n"   
        "\"(a*)\" matched \"$1\"\n"   
        "\"(b)\" matched \"$2\"\n");   
    std::cout << mr.format(fmt) << std::endl;   
    std::cout << std::endl;   
  
// index through submatches   
    for (size_t n = 0; n < mr.size(); ++n)   
        {   
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha   
            << mr[n].matched <<   
            " at position " << mr.position(n) << std::endl;   
        std::cout << "  " << mr.length(n)   
            << " chars, value == " << mr[n] << std::endl;   
        }   
    std::cout << std::endl;   
  
// iterate through submatches   
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)   
        {   
        std::cout << "next submatch: matched == " << std::boolalpha   
            << it->matched << std::endl;   
        std::cout << "  " << it->length()   
            << " chars, value == " << *it << std::endl;   
        }   
    std::cout << std::endl;   
  
// other members   
    std::cmatch mr1(mr);   
    mr = mr1;   
    mr.swap(mr1);   
  
    char buf[10];   
 *mr.format(&buf[0], "<$0>") = '\0';   
    std::cout << &buf[0] << std::endl;   
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;   
  
    std::cmatch::allocator_type al = mr.get_allocator();   
    std::cmatch::string_type str = std::string("x");   
    std::cmatch::size_type maxsiz = mr.max_size();   
    std::cmatch::char_type ch = 'x';   
    std::cmatch::difference_type dif = mr.begin() - mr.end();   
    std::cmatch::const_iterator cit = mr.begin();   
    std::cmatch::value_type val = *cit;   
    std::cmatch::const_reference cref = val;   
    std::cmatch::reference ref = val;   
  
    maxsiz = maxsiz;  // to quiet "unused" warnings   
    if (ref == cref)   
        ch = ch;   
    dif = dif;   
  
    return (0);   
    }  
  
```  
  
```Output  
prefix: matched == true, value == x  
whole match: 4 chars, value == caaa  
suffix: matched == true, value == y  
  
"c(a*)|(b)" matched "caaa"  
"(a*)" matched "aaa"  
"(b)" matched ""  
  
submatch[0]: matched == true at position 1  
  4 chars, value == caaa  
submatch[1]: matched == true at position 2  
  3 chars, value == aaa  
submatch[2]: matched == false at position 6  
  0 chars, value ==   
  
next submatch: matched == true  
  4 chars, value == caaa  
next submatch: matched == true  
  3 chars, value == aaa  
next submatch: matched == false  
  0 chars, value ==   
  
<caaa>  
empty == false  
```  
  
## <a name="see-also"></a>См. также  
 [\<regex>](../standard-library/regex.md)



