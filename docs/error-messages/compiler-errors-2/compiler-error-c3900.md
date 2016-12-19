---
title: "Ошибка компилятора C3900 | Microsoft Docs"
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
  - "C3900"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3900"
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3900
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": не допускается в текущей области  
  
 Блоки свойств могут содержать только объявления функций и определения встроенных функций.  Никакие другие члены, кроме функций, в блоках свойств не допускаются.  Не допускаются определения типов, операторы или дружественные функции.  Дополнительные сведения см. в описании [property](../../windows/property-cpp-component-extensions.md).  
  
 Определения событий могут содержать только функции и методы доступа.  
  
 Следующий пример приводит к возникновению ошибки C3900:  
  
```  
// C3900.cpp  
// compile with: /clr  
ref class X {  
   property int P {  
      void set(int);   // OK  
      int i;   // C3900 variable declaration  
   };  
};  
```  
  
 Следующий пример приводит к возникновению ошибки C3900:  
  
```  
// C3900b.cpp  
// compile with: /clr  
using namespace System;  
delegate void H();  
ref class X {  
   event H^ E {  
      int m;   // C3900  
  
      // OK  
      void Test() {}  
  
      void add( H^ h ) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```