---
title: "Ошибка компилятора C3804 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3804"
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Ошибка компилятора C3804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метод\_доступа\_свойства": все методы доступа для свойства должны быть либо статическими, либо не статическими  
  
 При определении нетривиальных свойств функции методов доступа могут быть либо статическими, либо функциями экземпляра \(но не обоих видов одновременно\).  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере возникает ошибка C3804.  
  
```  
// C3804.cpp  
// compile with: /c /clr  
ref struct A {  
  
   property int i {  
      static int get() {}  
      void set(int i) {}  
   }   // C3804 error  
  
   // OK  
   property int j {  
      int get() { return 0; }  
      void set(int i) {}  
   }  
  
   property int k {  
      static int get() { return 0; }  
      static void set(int i) {}  
   }  
};  
```