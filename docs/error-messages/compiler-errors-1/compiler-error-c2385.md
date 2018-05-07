---
title: Ошибка компилятора C2385 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2385
dev_langs:
- C++
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc152cd9d83b163632e64d1e2d8a0c5692439987
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2385"></a>Ошибка компилятора C2385
неоднозначный доступ «члена»  
  
 Элемент могут быть производными только один объект (наследуется от более чем одного объекта).  Чтобы устранить эту ошибку  
  
-   Сделать элемент однозначным, предоставляя приведения к типу.  
  
-   Необходимо переименуйте неоднозначные члены в базовых классах.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2385.  
  
```  
// C2385.cpp  
// C2385 expected  
#include <stdio.h>  
  
struct A   
{  
    void x(int i)   
    {  
        printf_s("\nIn A::x");  
    }  
};  
  
struct B   
{  
    void x(char c)   
    {  
        printf_s("\nIn B::x");  
    }  
};  
  
// Delete the following line to resolve.  
struct C : A, B {}  
  
// Uncomment the following 4 lines to resolve.  
// struct C : A, B   
// {  
//     using B::x;  
//     using A::x;  
// };  
  
int main()   
{  
    C aC;  
    aC.x(100);  
    aC.x('c');  
}  
  
struct C : A, B   
{  
    using B::x;  
    using A::x;  
};  
```