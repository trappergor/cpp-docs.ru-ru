---
title: "Ошибка компилятора C2993 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2993"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2993"
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2993
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": недопустимый тип для параметра шаблона "параметр", не являющегося типом.  
  
 Нельзя объявить шаблон с аргументом структуры или объединения.  Чтобы передавать структуры и объединения в качестве параметров шаблона, следует использовать указатели.  
  
 Следующий пример приводит к возникновению ошибки C2993:  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 Это ошибка может также возникать в результате процедуры компилятора по согласованию, выполненной для Visual Studio .NET 2003 : параметры шаблона с плавающей точкой, не являющегося типом, недопустимы.  Стандарты языка C\+\+ не позволяют использовать не являющиеся типами параметры шаблона с плавающей точкой.  
  
 В случае с шаблоном функции следует использовать аргумент функции для передачи в параметр с плавающей пикселем, не являющийся типом \(данный код функционирует в Visual Studio .NET 2003 и в версиях Visual Studio .NET для Visual C\+\+\).  Если речь идет о шаблоне класса, то простых путей решения проблемы не существует.  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```