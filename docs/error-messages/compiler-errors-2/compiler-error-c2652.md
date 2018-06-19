---
title: Ошибка компилятора C2652 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 576aef31268c0cdce09162fc367358e0ed044429
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232203"
---
# <a name="compiler-error-c2652"></a>Ошибка компилятора C2652
«Идентификатор»: недопустимый конструктор копии: первый параметр не должен быть «идентификатор»  
  
 Первый параметр в конструкторе копии имеет совпадает с типом класса, структуры или объединения, в котором они определены. Первый параметр может быть ссылкой на тип, но не самого типа.  
  
 Следующий пример приводит к возникновению ошибки C2651:  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```