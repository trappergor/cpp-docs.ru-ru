---
title: Ошибка компилятора C2786 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2786
dev_langs:
- C++
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29fd0d8cf22be29757abd775e1bb844cb1a1bfbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2786"></a>Ошибка компилятора C2786
«Тип»: недопустимый операнд для __uuidof  
  
 [__Uuidof](../../cpp/uuidof-operator.md) оператор принимает определяемый пользователем тип с присоединенным идентификатором GUID или объект такого типа определяемых пользователем.  Возможные причины:  
  
1.  Аргумент не определяемого пользователем типа.  
  
2.  `__uuidof` не удается извлечь идентификатор GUID из аргумента.  
  
 Следующий пример приводит к возникновению ошибки C2786:  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```