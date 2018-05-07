---
title: Ошибка компилятора C2258 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2258
dev_langs:
- C++
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d0e976edda871646a5bfa6c994d303a276b2f4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2258"></a>Ошибка компилятора C2258
недопустимый строгий синтаксис, требуется "= 0"  
  
 Чистая виртуальная функция объявлена с неправильным синтаксисом.  
  
 Следующий пример приводит к возникновению ошибки C2258:  
  
```  
// C2258.cpp  
// compile with: /c  
class A {  
public:  
   void virtual func1() = 1; // C2258  
   void virtual func2() = 0;   // OK  
};  
```