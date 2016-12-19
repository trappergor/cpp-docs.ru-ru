---
title: "Предупреждение компилятора (уровень 1) C4804 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4804"
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"операция" : небезопасное использование типа "bool" в операции  
  
 Это предупреждение предназначено для случая использования переменной или значения типа `bool` непредвиденным образом.  Например, предупреждение C4804 возникает при использовании таких операторов, как отрицательный унарный оператор \(**\-**\) или оператор дополнения \(`~`\).  Компилятор вычисляет выражение.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4804:  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```