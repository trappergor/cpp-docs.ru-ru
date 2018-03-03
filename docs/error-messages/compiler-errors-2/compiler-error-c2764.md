---
title: "Ошибка компилятора C2764 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2764
dev_langs:
- C++
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c623b48baf8a3ba41c7b14a4878e8473e0771cbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2764"></a>Ошибка компилятора C2764
«параметр»: параметр шаблона не используется или не выводится в частичной специализации «специализация»  
  
 Параметр шаблона не используется в частичной специализации. В результате частичной специализации непригодным для использования, так как не удается вывести параметр шаблона.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2764:  
  
```  
// C2764.cpp  
#include <stdio.h>  
template <class T1, class T2>  
struct S  {  
   int m_i;  
};  
  
template <class T1, class T2>  
struct S<int, T2*> {   // C2764  
// try the following line instead  
// struct S<T1(*)(T2), T2*> {  
   char m_c;  
};  
  
int main() {  
   S<int, char> s1;  
   S<void (*)(short), short *> s2;  
   s2.m_c = 10;  
   s1.m_i = s2.m_c;  
   printf_s("%d\n", s1.m_i);  
}  
```