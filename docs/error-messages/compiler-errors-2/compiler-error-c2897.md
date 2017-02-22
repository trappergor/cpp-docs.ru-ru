---
title: "Ошибка компилятора C2897 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2897"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2897"
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2897
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

деструктор\/метод завершения не может быть шаблоном функции  
  
 Перегрузка деструкторов или методов завершения невозможна, поэтому объявление деструктора в качестве шаблона \(приводящее к определению набора деструкторов\) не допускается.  
  
 Следующий пример приводит к возникновению ошибки C2897:  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2897.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2897.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```