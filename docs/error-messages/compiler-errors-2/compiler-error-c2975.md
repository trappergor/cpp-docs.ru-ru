---
title: "Ошибка компилятора C2975 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 07b2b96cd79364215c9a859a9fd0282768ff45e4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2975"></a>Ошибка компилятора C2975
«arg»: недопустимый аргумент шаблона для «тип», требуется константное выражение во время компиляции  
  
 Аргумент шаблона не соответствует объявлению шаблона; Константное выражение должно заключаться в угловые скобки. Переменные не разрешены в качестве фактических аргументов шаблона. Проверьте определение шаблона, чтобы найти правильные типы.  
  
 Следующий пример приводит к возникновению ошибки C2975:  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 C2975 также может возникнуть при использовании __LINE\_ \_ как константы времени компиляции с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md). Одним из решений будет компилироваться в [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) вместо **/ZI**.  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```
