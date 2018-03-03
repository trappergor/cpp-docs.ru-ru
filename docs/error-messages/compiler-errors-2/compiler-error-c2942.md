---
title: "Ошибка компилятора C2942 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2942
dev_langs:
- C++
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3f5a5a8941a1f0cc42127f5bda7d9c97a52bc18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2942"></a>Ошибка компилятора C2942
"класс": идентификатор класса типа переопределен как формальный аргумент функции  
  
 Универсальный класс или класс-шаблон нельзя использовать в качестве формального аргумента. Аргумент нельзя передать прямо в конструктор универсального класса или класса-шаблона.  
  
 Следующий пример приводит к возникновению ошибки C2942:  
  
```  
  
// C2942.cpp  
// compile with: /c  
template<class T>  
struct TC {};   
void f(int TC<int>) {}   // C2942  
  
// OK  
struct TC2 {};  
void f(TC2 i) {}  
```  
  
 Ошибка C2942 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2942b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
void f(int GC<int>) {}   // C2942  
ref struct GC2 { };  
void f(int GC2) {}  
```