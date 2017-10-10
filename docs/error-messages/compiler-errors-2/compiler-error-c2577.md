---
title: "Ошибка компилятора C2577 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2577
dev_langs:
- C++
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: df2e681274c21b639c6b188346b355167de7ce03
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2577"></a>Ошибка компилятора C2577
«член»: деструктор или метод завершения не может иметь тип возвращаемого значения  
  
 Деструктор или метод завершения не может возвращать значение `void` или любого другого типа. Удалить `return` оператора из определения деструктора.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2577.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```
