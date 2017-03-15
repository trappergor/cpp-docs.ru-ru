---
title: "Ошибка компилятора C3919 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3919"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3919"
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3919
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метод\_события": функция должна содержать тип "тип"  
  
 Метод доступа к событию был объявлен некорректно.  
  
 Дополнительные сведениями о событиях см. в разделе [событие](../../windows/event-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3919:  
  
```  
// C3919.cpp  
// compile with: /clr /c  
using namespace System;  
delegate void D(String^);  
ref class R {  
   event D^ e {  
      int add(int);   // C3919  
      int remove(int);   // C3919  
  
      void add(D^);   // OK  
      void remove(D^);   // OK  
   }  
};  
```