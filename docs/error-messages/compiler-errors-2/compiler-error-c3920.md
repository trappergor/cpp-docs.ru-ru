---
title: "Ошибка компилятора C3920 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3920
dev_langs:
- C++
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2e2bf82de4e32c2b0ae586c78c69ce474947c3ec
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3920"></a>Ошибка компилятора C3920
"оператор": не удается определить постфиксного инкремента или декремента WinRT или CLR оператор вызове постфиксного оператора WinRT или CLR вызывает соответствующий префикс WinRT или CLR operator (op_Increment/op_Decrement), но с постфиксной семантикой  
  
 Среда выполнения Windows и среда CLR не поддерживают постфиксный оператор, а пользовательские постфиксные операторы не разрешены.  Можно определить префиксный оператор, который будет использоваться для операций до и после приращения.  
  
 В следующем примере показано возникновение ошибки C3920 и приводятся сведения по ее устранению.  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```
