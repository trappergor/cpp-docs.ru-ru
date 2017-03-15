---
title: "Операторы &lt;filesystem&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
- std::experimental::filesystem::operator>>
dev_langs:
- C++
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 0875324fada10022291e8d33c2c2d6cf7276105c
ms.lasthandoff: 02/24/2017

---
# <a name="ltfilesystemgt-operators"></a>Операторы &lt;filesystem&gt;
Операторы выполняют лексическое сравнение двух путей как строк. Используйте **эквивалентную** функцию, чтобы определить, ссылаются ли два пути (например, относительный путь и абсолютный путь) на один и тот же файл или каталог на диске.  
  
```  
C:\root> D:\root: false  
C:\root> C:\root\sub: false  
C:\root> C:\roo: true  
```  
  
 Дополнительные сведения см. в разделе [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const path& left, const path& right) noexcept;  
```  
  
 Функция возвращает left.native() == right.native().  
  
## <a name="operator"></a>operator!=  
  
```  
bool operator!=(const path& left, const path& right) noexcept;  
```  
  
 Функция возвращает !(left == right).  
  
## <a name="operator"></a>operator<  
  
```  
bool operator<(const path& left, const path& right) noexcept;  
```  
  
 Функция возвращает left.native() < right.native().  
  
## <a name="operator"></a>operator<=  
  
```  
bool operator<=(const path& left, const path& right) noexcept;  
```  
  
 Функция возвращает !(right \< left).  
  
## <a name="operator"></a>operator>  
  
```  
bool operator>(const path& left, const path& right) noexcept;  
```  
  
 Функция возвращает right \< left.  
  
## <a name="operator"></a>operator>=  
  
```  
bool operator>=(const path& left, const path& right) noexcept;  
```  
  
 Функция возвращает !(left < right).  
  
## <a name="operator"></a>operator/  
  
```  
path operator/(const path& left, const path& right);
```  
  
 Функция выполняет:  
  
```  
basic_string<Elem, Traits> str;  
path ans = left;  
return (ans /= right);
```  
  
## <a name="operator"></a>operator<<  
  
```  
template <class Elem, class Traits>  
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```  
  
 Функция возвращает << pval.string\<Elem, Traits>().  
  
## <a name="operator"></a>operator>>  
  
```  
template <class Elem, class Traits>  
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```  
  
 Функция выполняет:  
  
```  
basic_string<Elem, Traits> str;  
is>> str;  
pval = str;  
return (is);
```  
  
## <a name="see-also"></a>См. также  
 [Класс path (библиотека стандартных шаблонов C++)](../standard-library/path-class.md)   
 [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)   
 [\<filesystem>](../standard-library/filesystem.md)


