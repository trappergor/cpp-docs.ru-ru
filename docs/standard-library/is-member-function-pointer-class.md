---
title: "Класс is_member_function_pointer | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_member_function_pointer
- std::is_member_function_pointer
- type_traits/std::is_member_function_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_member_function_pointer class
- is_member_function_pointer
ms.assetid: 02e372c4-2714-40f2-b376-2e10ca91c8ed
caps.latest.revision: 19
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 69b84eea79b1019e1be16c1c57977e95e00f58b5
ms.lasthandoff: 02/24/2017

---
# <a name="ismemberfunctionpointer-class"></a>Класс is_member_function_pointer
Проверяет, является ли тип указателем на функцию-член.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty>  
struct is_member_function_pointer;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является указателем на функцию-член или указателем `cv-qualified` на функцию-член; в противном случае — значение false.  
  
## <a name="example"></a>Пример  
  
```cpp  
// std__type_traits__is_member_function_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_function_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_function_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_function_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_member_function_pointer<trivial *> == false  
is_member_function_pointer<int trivial::*> == false  
is_member_function_pointer<int (functional::*)()> == true  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс is_member_pointer](../standard-library/is-member-pointer-class.md)

