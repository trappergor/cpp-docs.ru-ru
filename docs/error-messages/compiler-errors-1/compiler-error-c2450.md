---
title: Ошибка компилятора C2450 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2450
dev_langs:
- C++
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db8702703337d01bf8073dd31bcb54d876010c10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2450"></a>Ошибка компилятора C2450
выражение switch типа «тип» не допускается  
  
 `switch` Выражение принимает значение недопустимого типа. Его оценки должен быть целочисленный тип или тип класса с однозначным преобразованием в целочисленный тип. Если значение равно определяемого пользователем типа, вы должны предоставить оператор преобразования.  
  
 Следующий пример приводит к возникновению ошибки C2450:  
  
```  
// C2450.cpp  
class X {  
public:  
   int i;  
} x;  
  
class Y {  
public:  
   int i;  
   operator int() { return i; }   // conversion operator  
} y;  
  
int main() {  
   int j = 1;  
   switch ( x ) {   // C2450, x is not type int  
   // try the following line instead  
   // switch ( y ) {  
      default:  ;  
   }  
}  
```