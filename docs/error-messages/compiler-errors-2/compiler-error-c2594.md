---
title: "Ошибка компилятора C2594 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6a73e5202b90a0bc436d93be142162531c6d204
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2594"></a>Ошибка компилятора C2594
«оператор»: неоднозначные преобразования из «тип1» в «тип2»  
  
 Нет преобразования *тип1* для *тип2* являлось более прямым, чем другие. Мы советуем использовать два возможных решения к преобразованию *тип1* для *тип2*. Первый вариант предполагает определение прямого преобразования из *тип1* для *тип2*, и второй вариант заключается в указании последовательность преобразований из *тип1* для  *тип 2*.  
  
 Следующий пример приводит к возникновению ошибки C2594. Предложенный способ устранения ошибки представляет собой последовательность преобразований:  
  
```  
// C2594.cpp  
// compile with: /c  
struct A{};  
struct I1 : A {};  
struct I2 : A {};  
struct D : I1, I2 {};  
  
A *f (D *p) {  
   return (A*) (p);    // C2594  
  
// try the following line instead  
// return static_cast<A *>(static_cast<I1 *>(p));  
}  
```
