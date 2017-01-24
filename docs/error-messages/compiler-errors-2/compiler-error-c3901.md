---
title: "Ошибка компилятора C3901 | Microsoft Docs"
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
  - "C3901"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3901"
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3901
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"accessor\_function": должно иметь тип возвращаемого значения "type"  
  
 Как минимум один из типов возвращения метода "get" должен совпадать с типом свойства.  Дополнительные сведения см. в описании [property](../../windows/property-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3901:  
  
```  
// C3901.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String^ Name {  
      void get();   // C3901  
      // try the following line instead  
      // String^ get();  
   };  
};  
  
ref class Y {  
   property double values[int, int] {  
      int get(int, int);   // C3901  
      // try the following line instead  
      // double get(int, int);  
   };  
};  
```