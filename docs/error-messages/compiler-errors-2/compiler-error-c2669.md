---
title: Ошибка компилятора C2669 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2669
dev_langs:
- C++
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 642d2dd99c93b5af021503ffbb4975d1ff3c0db4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2669"></a>Ошибка компилятора C2669
функции-члена не разрешается в анонимном объединении  
  
[Анонимные объединения](../../cpp/unions.md#anonymous_unions) не может иметь функций-членов.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C2669:  
  
```cpp  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  