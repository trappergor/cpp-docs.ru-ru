---
title: "Класс add_pointer | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::add_pointer
dev_langs: C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a7af4a099d06b98ceb5fdd4bfb6dca0071c3f4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="addpointer-class"></a>Класс add_pointer
Создает указатель на тип из указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T>  
struct add_pointer;  
 
template <class T>
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>Параметры  
*T*  
Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
Определение типов `type`члена именует тот же тип как `remove_reference<T>::type*`. Псевдоним `add_pointer_t` является ярлыком для доступа к определению типа `type`.  
  
Поскольку его нельзя использовать для создания указателя из ссылки, `add_pointer` удаляет ссылку (если таковая имеется) из указанного типа, прежде чем создать указатель на тип. Следовательно, можно использовать тип с `add_pointer` вне зависимости от того, является ли данный тип ссылкой.  
  
## <a name="example"></a>Пример  
В следующем примере показано, что `add_pointer` типа аналогичен указателю на данный тип.  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_pointer_t<int> == int *  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс remove_pointer](../standard-library/remove-pointer-class.md)
