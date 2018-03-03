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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d4cca18672aad77e051ff4428dc115c53cd5ddad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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