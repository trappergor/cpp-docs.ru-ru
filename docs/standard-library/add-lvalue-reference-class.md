---
title: "Класс add_lvalue_reference | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- add_lvalue_reference
- type_traits/std::add_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_lvalue_reference
ms.assetid: 9933afc2-ad0d-465d-98fe-7d547fa3efe2
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
ms.openlocfilehash: a201572ed85d5bcf15435743ac0f8db8f08ede4b
ms.lasthandoff: 02/24/2017

---
# <a name="addlvaluereference-class"></a>Класс add_lvalue_reference
Делает из типа ссылку на тип.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T>  
struct add_lvalue_reference;  
 
template <class T>  
using add_lvalue_reference_t = typename add_lvalue_reference<T>::type;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `T` является ссылкой lvalue, в противном случае — `T&`.  
  
## <a name="example"></a>Пример  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
using namespace std;  
int main()  
{  
    int val = 0;  
    add_lvalue_reference_t<int> p = (int&)val;  
    p = p;  // to quiet "unused" warning   
    cout << "add_lvalue_reference_t<int> == "  
        << typeid(p).name() << endl;  
  
    return (0);  
}  
```  
  
```Output  
add_lvalue_reference_t<int> == int  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс remove_reference](../standard-library/remove-reference-class.md)

