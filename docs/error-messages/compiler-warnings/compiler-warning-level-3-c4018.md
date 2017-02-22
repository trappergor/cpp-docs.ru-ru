---
title: "Предупреждение компилятора (уровень 3) C4018 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4018"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4018"
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 3) C4018
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"выражение": несоответствие типов со знаком и без знака  
  
 Компилятору требуется сравнение чисел со знаком и без знака, чтобы преобразовать значение со знаком в значение без знака.  
  
 Данное предупреждение можно устранить путем приведения одного из двух типов при выполнении проверки типов со знаком и без знака.  
  
 Следующий пример приводит к возникновению ошибки C4018:  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```