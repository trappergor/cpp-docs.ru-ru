---
title: Ошибка компилятора C2353 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2353
dev_langs:
- C++
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6d5adf36760252a95502f38d2d7d64f9e090729
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2353"></a>Ошибка компилятора C2353
Спецификация исключения не допускается  
  
 Спецификации исключений недопустимы для функций-членов управляемых классов.  
  
 Следующий пример приводит к возникновению ошибки C2353:  
  
```  
// C2353.cpp  
// compile with: /clr /c  
ref class X {  
   void f() throw(int);   // C2353  
   void f();   // OK  
};  
```