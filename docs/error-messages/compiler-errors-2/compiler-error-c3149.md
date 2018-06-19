---
title: Ошибка компилятора C3149 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3149
dev_langs:
- C++
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c0441a7aebf86139aedbd5e45a7645db0a90b37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248512"
---
# <a name="compiler-error-c3149"></a>Ошибка компилятора C3149
«Тип»: невозможно использовать этот тип без верхнего уровня «char»  
  
 Объявление не указан правильно.  
  
 Например может определения типа CLR в глобальной области видимости и пытается создать переменную типа в определении. Так как глобальные переменные типов среды CLR не допускаются, компилятор создаст C3149.  
  
 Чтобы устранить эту ошибку, объявите переменные типов среды CLR в определении функции или типа.  
  
 Следующий пример приводит к возникновению ошибки C3149:  
  
```  
// C3149.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   // declare an array of value types   
   array< Int32 ^> IntArray;   // C3149  
   array< Int32>^ IntArray2;   // OK  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3149:  
  
```  
// C3149b.cpp  
// compile with: /clr /c  
delegate int MyDelegate(const int, int);  
void Test1(MyDelegate m) {}   // C3149  
void Test2(MyDelegate ^ m) {}   // OK  
```  
