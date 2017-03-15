---
title: "Класс is_base_of | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_base_of
- std::is_base_of
- type_traits/std::is_base_of
dev_langs:
- C++
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
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
ms.openlocfilehash: 22b1f7f93d82fbe5780352c11cb9024b8305d79c
ms.lasthandoff: 02/24/2017

---
# <a name="isbaseof-class"></a>Класс is_base_of
Проверяет, является ли один тип базовым для другого.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Base, class Derived>  
struct is_base_of;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Базовый класс для проверки.  
  
 `Derived`  
 Производный тип для проверки.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа имеет значение true, если тип `Base` является базовым классом для типа `Derived`, в противном случае — значение false.  
  
## <a name="example"></a>Пример  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
struct base   
    {   
    int val;   
    };   
  
struct derived   
    : public base   
    {   
    };   
  
int main()   
    {   
    std::cout << "is_base_of<base, base> == " << std::boolalpha   
        << std::is_base_of<base, base>::value << std::endl;   
    std::cout << "is_base_of<base, derived> == " << std::boolalpha   
        << std::is_base_of<base, derived>::value << std::endl;   
    std::cout << "is_base_of<derived, base> == " << std::boolalpha   
        << std::is_base_of<derived, base>::value << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
is_base_of<base, base> == true  
is_base_of<base, derived> == true  
is_base_of<derived, base> == false  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
Класс  [is_convertible](../standard-library/is-convertible-class.md)

