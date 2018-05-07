---
title: Ошибка компилятора C2933 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2933
dev_langs:
- C++
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 148bf679888a3801327648aa2bc1dd59a128ded7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2933"></a>Ошибка компилятора C2933
"класс": идентификатор класса типа переопределен как член typedef "идентификатор"  
  
 Универсальный класс или класс-шаблон нельзя использовать в качестве члена `typedef` .  
  
 Следующий пример приводит к возникновению ошибки C2933:  
  
```  
// C2933.cpp  
// compile with: /c  
template<class T> struct TC { };   
struct MyStruct {  
   typedef int TC<int>;   // C2933  
};  
  
struct TC2 { };   
struct MyStruct2 {  
   typedef int TC2;  
};  
```  
  
 Ошибка C2933 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C2933b.cpp  
// compile with: /clr /c  
generic<class T> ref struct GC { };  
struct MyStruct {  
   typedef int GC<int>;   // C2933  
};  
  
ref struct GC2 { };  
struct MyStruct2 {  
   typedef int GC2;  
};  
```