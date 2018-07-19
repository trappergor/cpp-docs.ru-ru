---
title: Ошибка компилятора C3182 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 503ad6d17b197392967681bfdf4e921aa21dc3e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254626"
---
# <a name="compiler-error-c3182"></a>Ошибка компилятора C3182
«класс»: объявление члена с помощью объявления или доступа недопустимо в пределах управляемого типа или WinRTtype  
  
 Объект [с помощью](../../cpp/using-declaration.md) объявление является недопустимым во всех формах управляемых классов.  
  
 В следующем примере показано возникновение ошибки C3182 и приводятся сведения по ее устранению.  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  
