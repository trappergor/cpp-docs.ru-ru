---
title: "Ошибка компилятора C2663 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a9efe20b4a80b9ff6f337d32acd35320125008dc
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2663"></a>Ошибка компилятора C2663
«функция»: числовые перегрузки не имеют действительных преобразований для указателя «this»  
  
 Компилятору не удалось преобразовать `this` на любой из перегруженных версий функции-члена.  
  
 Эта ошибка может вызываться вызов значение, отличное от`const` функции-члена `const` объекта.  Возможные решения:  
  
1.  Удалите `const` из объявления объекта.  
  
2.  Добавить `const` к одной из перегрузок функции-члена.  
  
 Следующий пример приводит к возникновению ошибки C2663:  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```
