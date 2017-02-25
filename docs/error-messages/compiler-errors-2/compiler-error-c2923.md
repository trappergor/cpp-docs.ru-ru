---
title: "Ошибка компилятора C2923 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2923"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2923"
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2923
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": "идентификатор" не является допустимым аргументом типа шаблона для параметра "параметр"  
  
 В списке аргументов пропущен тип, необходимый для создания экземпляра шаблона или универсального класса. Проверьте объявление шаблона или универсального класса.  
  
 Следующий пример приводит к возникновению ошибки C2923:  
  
```  
// C2923.cpp template <class T> struct TC {}; int x; int main() { TC<x>* tc2;   // C2923 TC<int>* tc2;   // OK }  
```  
  
 Ошибка C2923 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C2923b.cpp // compile with: /clr /c generic <class T> ref struct GC {}; int x; int main() { GC<x>^ gc2;   // C2923 GC<int>^ gc2;   // OK }  
```