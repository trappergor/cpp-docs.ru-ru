---
title: "Ошибка компилятора C2767 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2767
dev_langs:
- C++
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9147d85afaee50a2b0c2e47debe5603d6e208712
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2767"></a>Ошибка компилятора C2767
управляемые или WinRTarray измерения несоответствие: требуется N аргументов, представлено M  
  
 Неправильный формат объявления управляемого массива или массива WinRT. Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).  
  
 В следующем примере показано возникновение ошибки C2767 и приводятся сведения по ее устранению.  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```
