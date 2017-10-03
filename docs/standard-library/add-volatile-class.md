---
title: "Класс add_volatile | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 7e652a784276d01c572ffad0379a20359a7b39f2
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="addvolatile-class"></a>Класс add_volatile
Создает тип volatile из указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Ty>  
struct add_volatile;  
 
template <class T>
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
### <a name="parameters"></a>Параметры  
*T*  
Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
Экземпляр `add_volatile<T>` содержит определение типа члена `type`, который является *T*, если *T* является ссылкой, функцией или типом с квалификатором volatile; в противном случае — `volatile` *T*. Псевдоним `add_volatile_t` является ярлыком для доступа к определению типа `type`. 
  
## <a name="example"></a>Пример  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
} 
```  
  
```Output  
add_volatile<int> == int  
```  
  
## <a name="requirements"></a>Требования  

**Заголовок:** \<type_traits>  
  
**Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
[<type_traits>](../standard-library/type-traits.md)   
[Класс remove_volatile](../standard-library/remove-volatile-class.md)

