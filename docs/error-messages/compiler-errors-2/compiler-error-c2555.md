---
title: "Ошибка компилятора C2555 | Microsoft Docs"
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
  - "C2555"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2555"
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2555
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс1::функция 1": возвращаемый тип перегруженной виртуальной функции отличается и не является ковариантным для "класс2::функция 2"  
  
 Виртуальная функция и производная переопределенной функции имеют идентичные списки параметров, но различные типы возвращаемого значения.  Переопределенная функция в производном классе не может отличаться от виртуальной функции в базовом классе только типом возвращаемого значения.  
  
 Чтобы устранить данную ошибку, следует выполнить приведение возвращаемого значения после вызова виртуальной функции.  
  
 Данная ошибка также может возникать при выполнении компиляции с параметром \/clr.   Например, эквивалентом Visual C\+\+ следующему объявлению в C\#:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 является  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Дополнительные сведения об ошибке C2555 см. в статье информационной базы данных Q240862.  
  
 Следующий пример приводит к возникновению ошибки C2555:  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```