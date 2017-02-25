---
title: "Ошибка компилятора C3491 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3491"
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"var": параметр, передаваемый по значению, не может быть изменен в лямбда\-выражении, объявленном как неизменяемое  
  
 Неизменяемое лямбда\-выражение не может изменить значение переменной, передаваемой по значению.  
  
### Исправление ошибки  
  
-   Объявите лямбда\-выражение с ключевым словом `mutable` или  
  
-   передайте переменную по ссылке в список передачи лямбда\-выражения.  
  
## Пример  
 В приведенном ниже примере возникает ошибка C3491, так как тело неизменяемого лямбда\-выражения изменяет передаваемую переменную `m`:  
  
```  
// C3491a.cpp int main() { int m = 55; [m](int n) { m = n; }(99); // C3491 }  
```  
  
## Пример  
 В приведенном ниже примере ошибка C3491 устраняется путем объявления лямбда\-выражения с ключевым словом `mutable`:  
  
```  
// C3491b.cpp int main() { int m = 55; [m](int n) mutable { m = n; }(99); }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)