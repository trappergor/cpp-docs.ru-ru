---
title: "Класс regex_error | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: a0336bce168edc8b4c50639b1e3ace4f82e7c971
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="regexerror-class"></a>Класс regex_error
Сообщает о неверном объекте basic_regex.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class regex_error  
 : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;

 
 };  
```  
  
## <a name="remarks"></a>Примечания  
 Класс описывает объект исключения, создаваемый для уведомления об ошибке в построении или использовании объекта `basic_regex` .  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<regex>  
  
 **Пространство имен:** std  
  
##  <a name="code"></a>  regex_error::code  
 Возвращает код ошибки.  
  
```  
regex_constants::error_code code() const;
```  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает значение, которое было передано в конструктор объекта.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__regex_error_code.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
##  <a name="regex_error"></a>  regex_error::regex_error  
 Создает объект.  
  
```  
regex_error(regex_constants::error_code error);
```  
  
### <a name="parameters"></a>Параметры  
 `error`  
 Код ошибки.  
  
### <a name="remarks"></a>Примечания  
 Конструктор создает объект, содержащий значение `error`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// std__regex__regex_error_construct.cpp   
// compile with: /EHsc   
#include <regex>   
#include <iostream>   
  
int main()   
    {   
    std::regex_error paren(std::regex_constants::error_paren);   
  
    try   
        {   
        std::regex rx("(a");   
        }   
    catch (const std::regex_error& rerr)   
        {   
        std::cout << "regex error: "   
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
            << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
```Output  
regex error: unbalanced parentheses  
```  
  
## <a name="see-also"></a>См. также  
[\<regex>](../standard-library/regex.md)  
[Класс regex_constants](../standard-library/regex-constants-class.md)  
[Функции \<regex>](../standard-library/regex-functions.md)  
[Класс regex_iterator](../standard-library/regex-iterator-class.md)  
[Операторы \<regex>](../standard-library/regex-operators.md)  
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Класс regex_traits](../standard-library/regex-traits-class.md)  
[Определения типов \<regex>](../standard-library/regex-typedefs.md)  

