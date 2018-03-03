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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2d48df0ef5d4c5a4dff649a54132e75969d92e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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