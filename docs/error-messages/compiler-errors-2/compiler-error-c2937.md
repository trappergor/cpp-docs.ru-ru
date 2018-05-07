---
title: Ошибка компилятора C2937 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2937
dev_langs:
- C++
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4972c57963801419be08e60354a9464350cb6ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2937"></a>Ошибка компилятора C2937
"класс": идентификатор класса типа переопределен как глобальное определение типа (typedef)  
  
 Универсальный класс или класс шаблона нельзя использовать в качестве глобального `typedef`.  
  
 Следующий пример приводит к возникновению ошибки C2937:  
  
```  
// C2937.cpp  
// compile with: /c  
template<class T>   
struct TC { };  
typedef int TC<int>;   // C2937  
typedef TC<int> c;   // OK  
```  
  
 Ошибка C2937 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C2937b.cpp  
// compile with: /clr  
generic<class T>  
ref struct GC { };  
typedef int GC<int>;   // C2937  
typedef GC<int> xx;   // OK  
```