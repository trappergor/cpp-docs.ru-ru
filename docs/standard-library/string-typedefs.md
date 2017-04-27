---
title: "Определения типов &lt;string&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ba8cd6e49f490718beb8fdc216781d8950aedbfb
ms.lasthandoff: 02/24/2017

---
# <a name="ltstringgt-typedefs"></a>Определения типов &lt;string&gt;
||||  
|-|-|-|  
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|  
|[wstring](#wstring)|  
  
##  строка <a name="string"></a>  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md) элементами типа `char`.  
  
 Другие определения типов, описывающие специализацию `basic_string`, включают [wstring](../standard-library/string-typedefs.md#wstring), [u16string](../standard-library/string-typedefs.md#u16string) и [u32string](../standard-library/string-typedefs.md#u32string).  
  
```cpp  
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```  
  
### <a name="remarks"></a>Примечания  
 Следующие объявления являются равнозначными:  
  
```cpp  
string str("");

basic_string<char> str("");
```  
  
 Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string__basic_string).  
  
##  <a name="u16string"></a>  u16string  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md) элементами типа `char16_t`.  
  
 Другие определения типов, описывающие специализацию `basic_string`, включают [wstring](../standard-library/string-typedefs.md#wstring), [string](../standard-library/string-typedefs.md#string) и [u32string](../standard-library/string-typedefs.md#u32string).  
  
```cpp  
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```  
  
### <a name="remarks"></a>Примечания  
 Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string__basic_string).  
  
##  <a name="u32string"></a>  u32string  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md) элементами типа `char32_t`.  
  
 Другие определения типов, описывающие специализацию `basic_string`, включают [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) и [wstring](../standard-library/string-typedefs.md#wstring).  
  
```cpp  
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```  
  
### <a name="remarks"></a>Примечания  
 Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string__basic_string).  
  
##  <a name="wstring"></a>  wstring  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md) элементами типа `wchar_t`.  
  
 Другие определения типов, описывающие специализацию `basic_string`, включают [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) и [u32string](../standard-library/string-typedefs.md#u32string).  
  
```cpp  
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```  
  
### <a name="remarks"></a>Примечания  
 Следующие объявления являются равнозначными:  
  
```cpp  
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```  
  
 Список конструкторов строк см. в разделе [basic_string::basic_string](../standard-library/basic-string-class.md#basic_string__basic_string).  
  
> [!NOTE]
>  Размер `wchar_t` определяется при реализации. Если код исходит из определенного размера `wchar_t`, проверьте реализацию вашей платформы (например, с помощью `sizeof(wchar_t)`). Если требуется тип строчного символа, ширина которого гарантированно останется одинаковой на всех платформах, используйте [string](../standard-library/string-typedefs.md#string), [u16string](../standard-library/string-typedefs.md#u16string) или [u32string](../standard-library/string-typedefs.md#u32string).  
  
## <a name="see-also"></a>См. также  
 [\<string>](../standard-library/string.md)




