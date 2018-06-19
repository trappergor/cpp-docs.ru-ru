---
title: Ошибка компилятора C2437 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2437
dev_langs:
- C++
helpviewer_keywords:
- C2437
ms.assetid: 2d2b3c6c-856a-4b27-ae10-64813b3e5483
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc9c619ac361fcbe2d095407b4030a2e38ada8ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33224428"
---
# <a name="compiler-error-c2437"></a>Ошибка компилятора C2437
«Идентификатор»: уже инициализирован.  
  
 Объект можно инициализировать только один раз.  
  
 Следующий пример приводит к возникновению ошибки C2437:  
  
```  
// C2437.cpp  
// compile with: /c  
class A {  
public:  
   A(int i) {}  
};  
  
class B : A {  
   B() : A(1), A(2) {}   // C2437  
   B() : A(1) {}   // OK  
};  
```