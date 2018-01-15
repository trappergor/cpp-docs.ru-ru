---
title: "Класс is_placeholder | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: functional/std::is_placeholder
dev_langs: C++
helpviewer_keywords: is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9aa19cb8fceb167cd98c94583e47f2e9c1227333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

