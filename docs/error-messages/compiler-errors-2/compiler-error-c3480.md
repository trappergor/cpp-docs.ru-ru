---
title: "Ошибка компилятора C3480 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3480"
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": передаваемая переменная в лямбда\-выражении должна быть из внешней области видимости функции  
  
 Передаваемая переменная в лямбда\-выражении не относится к внешней области видимости функции.  
  
### Исправление ошибки  
  
-   Удалите переменную из списка передачи лямбда\-выражения.  
  
## Пример  
 Приведенный ниже пример вызывает ошибку C3480, так как переменная `global` не относится к внешней области видимости функции.  
  
```  
// C3480a.cpp int global = 0; int main() { [&global] { global = 5; }(); // C3480 }  
```  
  
## Пример  
 В приведенном ниже примере ошибка C3480 устраняется путем удаления переменной `global` из списка передачи лямбда\-выражения.  
  
```  
// C3480b.cpp int global = 0; int main() { [] { global = 5; }(); }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)