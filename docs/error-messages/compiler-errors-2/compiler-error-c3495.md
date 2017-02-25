---
title: "Ошибка компилятора C3495 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3495"
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var : передаваемый параметр лямбда\-выражения должен иметь длительность автоматического хранения  
  
 Вы не можете передавать переменную, которая не поддерживает автоматическую длительность хранения, например переменную, помеченную как `static` или `extern`.  
  
### Исправление ошибки  
  
-   Не передавайте переменную по `static` или `extern` в список передаваемых параметров лямбда\-выражения.  
  
## Пример  
 В следующем примере возникает ошибка C3495, так как в списке передаваемых параметров лямбда\-выражения присутствует переменная `static``n`.  
  
```  
// C3495.cpp int main() { static int n = 66; [&n]() { return n; }(); // C3495 }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)   
 [\(NOTINBUILD\)Спецификаторы классов хранения](http://msdn.microsoft.com/ru-ru/10b3d22d-cb40-450b-994b-08cf9a211b6c)