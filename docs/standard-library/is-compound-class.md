---
title: "Класс is_compound | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_compound
- type_traits/std::is_compound
dev_langs:
- C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: 21
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
ms.openlocfilehash: 2137c8a92c3821137ab1669b4b9162fd309d0fbe
ms.lasthandoff: 02/24/2017

---
# <a name="iscompound-class"></a>Класс is_compound
Проверяет, является ли указанный тип фундаментальным.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty>  
struct is_compound;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит `false`, если тип `Ty` — фундаментальный тип (т. е., если [is_fundamental](../standard-library/is-fundamental-class.md)`<``Ty``>` имеет значение `true`). В противном случае он имеет значение `true`. Таким образом, предикат имеет значение `true`, если `Ty` является типом массива, типом функции, указателем на `void`, на объект или функцию, ссылкой, классом, объединением, перечислением или указателем на нестатический член класса или форму *cv-qualified* одного из них.  
  
## <a name="example"></a>Пример  
  
```cpp  
// std__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_compound<trivial> == true  
is_compound<int[]> == true  
is_compound<int()> == true  
is_compound<int&> == true  
is_compound<void *> == true  
is_compound<int> == false  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
Класс  [is_class](../standard-library/is-class-class.md)

