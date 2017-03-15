---
title: "Ошибка компилятора C2776 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2776"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2776"
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2776
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

в свойстве может быть указан только один метод "get"  
  
 Только одна функция `get` может быть указана в расширенном атрибуте [property](../../cpp/property-cpp.md).  Эта ошибка возникает при задании нескольких функций `get`.  
  
 Следующий пример приводит к возникновению ошибки C2776:  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```