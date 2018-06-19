---
title: Ошибка компилятора C2824 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2824
dev_langs:
- C++
helpviewer_keywords:
- C2824
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc654f60d9494480e0551f4de3ec1e041938cea2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237168"
---
# <a name="compiler-error-c2824"></a>Ошибка компилятора C2824
Тип возвращаемого значения для «operator new» должен быть "void *"  
  
 Не на основе указателей, при перегрузке оператора `new` должен возвращать `void *`.  
  
 Следующий пример приводит к возникновению ошибки C2824:  
  
```  
// C2824.cpp  
// compile with: /c  
class   A {  
   A* operator new(size_t i, char *m);   // C2824  
   // try the following line instead  
   // void* operator new(size_t i, char *m);  
};  
```