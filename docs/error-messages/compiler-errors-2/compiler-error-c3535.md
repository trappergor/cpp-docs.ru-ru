---
title: "Ошибка компилятора C3535 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3535
dev_langs: C++
helpviewer_keywords: C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5797d644ec13ed89bad3ddcda23be109df067b03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3535"></a>Ошибка компилятора C3535
Невозможно вывести тип для «тип1» в «тип2»  
  
 Тип переменной, объявленной с `auto` ключевое слово не может быть выведен из типа выражения инициализации. Например, эта ошибка возникает, если выражение инициализации равно `void`, который не является типом.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что тип выражения инициализации не является `void`.  
  
2.  Убедитесь, что объявление не является указателем на основной тип. Дополнительные сведения см. в разделе [базовые типы](../../cpp/fundamental-types-cpp.md).  
  
3.  Убедитесь, что, если объявление является указателем на тип, выражение инициализации является типом указателя.  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, поскольку выражение инициализации равно `void`.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, поскольку оператор объявляет переменную `x` как указатель на выведенный тип, но тип инициализатора выражения типа double. Как следствие компилятор не может вывести тип переменной.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Пример  
 Следующий пример вызывает ошибку C3535, так как переменная `p` объявляет указатель на выведенный тип, а выражение инициализации не является типом указателя.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевое слово Auto](../../cpp/auto-keyword.md)   
 [Базовые типы](../../cpp/fundamental-types-cpp.md)