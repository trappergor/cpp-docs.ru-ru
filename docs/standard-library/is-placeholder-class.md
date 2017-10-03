---
title: "Класс is_placeholder | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::is_placeholder
dev_langs:
- C++
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.openlocfilehash: e50b427abcdaf8388ae35a0fef448603698e220a
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="isplaceholder-class"></a>Класс is_placeholder
Проверяет, является ли тип заполнителем.  
  
## <a name="syntax"></a>Синтаксис  
  
struct is_placeholder {  
   static const int value;  
   };  
  
## <a name="remarks"></a>Примечания  
 Значение константы `value` равно 0, если тип `Ty` не является заполнителем. В противном случае значение — это положение аргумента вызова функции, к которому он привязывается. Используется для определения значения `N` n-ного заполнителя `_N`.  
  
## <a name="example"></a>Пример  
  
```cpp  
// std__functional__is_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
using namespace std::placeholders;   
  
template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}  
```  
  
```Output  
0  
3  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<functional>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Объект _1](../standard-library/1-object.md)


