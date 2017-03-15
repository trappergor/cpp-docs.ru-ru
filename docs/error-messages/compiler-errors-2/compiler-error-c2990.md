---
title: "Ошибка компилятора C2990 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2990"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2990"
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Ошибка компилятора C2990
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": тип, не являющийся классом, уже объявлен как тип, являющийся классом  
  
 Не являющийся универсальным класс или класс шаблона переопределяет универсальный класс или класс шаблона.  Следует проверить файлы заголовков на наличие противоречий.  
  
 Следующий пример приводит к возникновению ошибки C2990:  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 Ошибка C2990 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 Ошибка C2990 также может возникать вследствие критических изменений в компиляторе Visual C\+\+ для Visual C\+\+ 2005; теперь компилятору требуется, чтобы несколько объявлений для одного и того же типа были идентичными в части указания шаблона.  
  
 Следующий пример приводит к возникновению ошибки C2990:  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```