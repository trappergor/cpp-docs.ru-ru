---
title: "Предупреждение компилятора (уровень&#160;1) C4807 | Microsoft Docs"
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
  - "C4807"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4807"
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;1) C4807
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"операция": небезопасное смешение типа "тип" и битового поля со знаком типа "тип"  
  
 Это предупреждение возникает при сравнении однобитового поля со знаком с переменной `bool`. Так как однобитовое поле со знаком может содержать только значения –1 или 0, его небезопасно сравнивать с `bool`. Сочетание `bool` и однобитовых полей без знака не вызывает предупреждений, так как эти поля идентичны `bool` и могут содержать только 0 или 1.  
  
## Пример  
 Следующий пример приводит к возникновению предупреждения C4807:  
  
```  
// C4807.cpp // compile with: /W1 typedef struct bitfield { signed mybit : 1; } mybitfield; int main() { mybitfield bf; bool b = true; // try.. // int b = true; bf.mybit = -1; if (b == bf.mybit) {   // C4807 b = false; } }  
```