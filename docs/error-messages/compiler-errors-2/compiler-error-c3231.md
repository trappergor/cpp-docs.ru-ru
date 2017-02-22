---
title: "Ошибка компилятора C3231 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3231"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3231"
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3231
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"аргумент": аргумент типа шаблона не может использовать параметр универсального типа  
  
 Экземпляры шаблонов создаются во время компиляции, а универсальные шаблоны создаются во время выполнения.  Поэтому невозможно создать универсальный код, вызывающий шаблон, поскольку шаблон не может быть создан во время выполнения, когда универсальный тип известен.  
  
 Следующий пример приводит к возникновению ошибки C3231:  
  
```  
// C3231.cpp  
// compile with: /clr /LD  
template <class T> class A;  
  
generic <class T>  
ref class C {  
   void f() {  
      A<T> a;   // C3231  
   }  
};  
```