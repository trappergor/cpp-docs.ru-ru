---
title: "Ошибка компилятора C2785 | Microsoft Docs"
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
  - "C2785"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2785"
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2785
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"объявление1" и "объявление2" имеют различные возвращаемые типы  
  
 Возвращаемый тип специализации шаблона функции отличен от возвращаемого типа шаблона основной функции.  
  
### Исправление этой ошибки  
  
1.  Проверьте все специализации шаблона функции на согласованность.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2785:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```