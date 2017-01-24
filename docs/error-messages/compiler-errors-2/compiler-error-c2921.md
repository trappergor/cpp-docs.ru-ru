---
title: "Compiler Error C2921 | Microsoft Docs"
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
  - "C2921"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2921"
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C2921
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

переопределение: class: шаблон класса или универсальный тип повторно объявляется как type  
  
 Универсальный или шаблонный класс имеет несколько объявлений, которые не эквивалентны.  Чтобы устранить эту ошибку, используйте разные имена для различных типов или удалите переопределение имени типа.  
  
 Следующий пример приводит к возникновению ошибки C2921:  
  
```  
// C2921.cpp  
// compile with: /c  
template <class T> struct TC2 {};  
typedef int TC2;   // C2921  
// try the following line instead  
// typedef struct TC2<int> x;   // OK - declare a template instance   
```  
  
 Ошибка C2921 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C2921b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC2 {};  
typedef int GC2;   // C2921  
// try the following line instead  
// typedef ref struct GC2<int> x;  
```