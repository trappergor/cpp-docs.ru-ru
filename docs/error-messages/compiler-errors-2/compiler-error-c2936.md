---
title: "Ошибка компилятора C2936 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2936
dev_langs:
- C++
helpviewer_keywords:
- C2936
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c7949f958a6656c5e29210fcc4533c5730d18e02
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2936"></a>Ошибка компилятора C2936
"класс": идентификатор класса типа переопределен как глобальная переменная данных  
  
 Универсальный класс или класс шаблона нельзя использовать в качестве глобальной переменной данных.  
  
 Эта ошибка может возникнуть при неправильной расстановке скобок.  
  
 Следующий пример приводит к возникновению ошибки C2936:  
  
```  
// C2936.cpp  
// compile with: /c  
template<class T> struct TC { };   
int TC<int>;   // C2936  
  
// OK  
struct TC2 { };   
int TC2;  
```  
  
 Ошибка C2936 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2936b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
int GC<int>;   // C2936  
  
// OK  
ref struct GC2 {};  
int GC2;  
```
