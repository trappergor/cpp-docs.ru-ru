---
title: "Предупреждение компилятора (уровень&#160;4) C4130 | Microsoft Docs"
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
  - "C4130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4130"
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;4) C4130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"оператор": логическая операция с адресом строковой константы  
  
 Использование оператора с адресом строкового литерала создает непредвиденный код.  
  
 Следующий пример приводит к возникновению ошибки C4130:  
  
```  
// C4130.cpp // compile with: /W4 int main() { char *pc; pc = "Hello"; if (pc == "Hello") // C4130 { } }  
```  
  
 Оператор **if** сравнивает значение, сохраненное в указателе `pc` на адрес строки "Hello", который выделяется отдельно каждый раз, когда строка встречается в коде. Оператор **if** не сравнивает строку, на которую указывает `pc`, со строкой "Hello".  
  
 Для сравнения строк используйте функцию `strcmp`.