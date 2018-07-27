---
title: Ошибка компилятора предупреждение (уровень 4) C4913 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4913
dev_langs:
- C++
helpviewer_keywords:
- C4913
ms.assetid: b94aa52e-6029-4170-9134-017714931546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbac505559f07e2c58b76970ba33b11a109d90b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294626"
---
# <a name="compiler-warning-level-4-c4913"></a>Предупреждение компилятора (уровень 4) C4913
**пользовательский двоичный оператор "," существует, но ни одной перегрузке не удалось преобразовать все операнды, по умолчанию использован встроенный двоичный оператор ","**  
  
 Вызов встроенного оператора "запятая" произошел в программе, которая также имела перегруженный оператор "запятая"; преобразование, на которое вы, возможно, рассчитывали, не произошло.  
  
 В следующем примере возникает ошибка C4913.  
  
```  
// C4913.cpp  
// compile with: /W4  
struct A  
{  
};  
  
struct S  
{  
};  
  
struct B  
{  
   // B() { }  
   // B(S &s) { s; }  
};  
  
B operator , (A a, B b)     
{  
   a;  
   return b;  
}  
  
int main()  
{  
   A a;  
   B b;  
   S s;  
  
   a, b;   // OK calls user defined operator  
   a, s;   // C4913 uses builtin comma operator  
           // uncomment the conversion code in B to resolve.  
}  
```