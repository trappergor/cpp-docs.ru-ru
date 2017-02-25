---
title: "Ошибка компилятора C2514 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2514"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2514"
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2514
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": класс не имеет конструкторов  
  
 Структура, класс или объединение не имеет конструктора со списком параметров, соответствующих параметрам, используемым для создания их экземпляров.  
  
 Класс должен быть полностью объявлен прежде, чем будет создан его экземпляр.  
  
 Следующий пример приводит к возникновению ошибки C2514:  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```