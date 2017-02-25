---
title: "Ошибка компилятора C3799 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3799"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3799"
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Ошибка компилятора C3799
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

список параметров индексированного свойства не может быть пустым  
  
 Неправильно объявлено индексированное свойство.  Дополнительные сведения см. в разделе [Практическое руководство. Использование индексированных свойств](../../misc/how-to-use-indexed-properties.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3799.  
  
```  
// C3799.cpp  
// compile with: /clr /c  
ref struct C {  
   property int default[] {   // C3799  
   // try the following line instead  
   // property int default[int] {  
      int get(int index) { return 0; }  
      void set(int index, int value) {}  
   }  
};  
```