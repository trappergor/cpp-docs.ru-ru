---
title: "Класс is_enum | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_enum
- type_traits/std::is_enum
dev_langs:
- C++
helpviewer_keywords:
- is_enum class
- is_enum
ms.assetid: df3b00b7-4f98-4b3a-96ce-10ad958ee69c
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
ms.openlocfilehash: 1e57d67f920b6742c8ba6b732675c00a8b0df992
ms.lasthandoff: 02/24/2017

---
# <a name="isenum-class"></a>Класс is_enum
Проверяет, является ли тип перечислением.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty>  
struct is_enum;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа имеет значение true, если тип `Ty` является типом перечисления или формой `cv-qualified` типа перечисления, в противном случае — значение false.  
  
## <a name="example"></a>Пример  
  
```cpp  
// std__type_traits__is_enum.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
enum color {   
    red, greed, blue};   
  
int main()   
    {   
    std::cout << "is_enum<trivial> == " << std::boolalpha   
        << std::is_enum<trivial>::value << std::endl;   
    std::cout << "is_enum<color> == " << std::boolalpha   
        << std::is_enum<color>::value << std::endl;   
    std::cout << "is_enum<int> == " << std::boolalpha   
        << std::is_enum<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_enum<trivial> == false  
is_enum<color> == true  
is_enum<int> == false  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс is_integral](../standard-library/is-integral-class.md)

