---
title: "Класс remove_const | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_const
dev_langs: C++
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4419fc7f08cd15dd36c51544472a43b4134826d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="removeconst-class"></a>Класс remove_const
Создает неконстантный тип из типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T>  
struct remove_const;
```  
  
```  
template <class T>  
using remove_const_t = typename remove_const<T>::type;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр `remove_const<T>` содержит измененный тип, т. е. `T1`, если `T` имеет форму `const T1`; в противном случае — `T`.  
  
## <a name="example"></a>Пример  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_const_t<const int>*)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_const_t<const int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_const_t<const int> == int  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс add_const](../standard-library/add-const-class.md)   
 [Класс remove_cv](../standard-library/remove-cv-class.md)
