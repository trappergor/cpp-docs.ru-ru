---
title: "Ошибка компилятора C3493 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3493"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3493"
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3493
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная" нельзя передать неявно, поскольку не задан режим передачи по умолчанию  
  
 Предложение пустой передачи лямбда\-выражения \(`[]`\) указывает на то, что лямбда\-выражение не передает никаких переменных явно или неявно.  
  
### Исправление ошибки  
  
-   Укажите режим передачи по умолчанию или  
  
-   явно передайте одну или несколько переменных.  
  
## Пример  
 В приведенном ниже примере возникает ошибка C3493, так как в нем изменяется внешняя переменная, но указывается предложение пустой передачи.  
  
```  
// C3493a.cpp int main() { int m = 55; [](int n) { m = n; }(99); // C3493 }  
```  
  
## Пример  
 В приведенном ниже примере ошибка C3493 устраняется путем указания передачи по ссылке в качестве режима передачи по умолчанию.  
  
```  
// C3493b.cpp int main() { int m = 55; [&](int n) { m = n; }(99); }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)