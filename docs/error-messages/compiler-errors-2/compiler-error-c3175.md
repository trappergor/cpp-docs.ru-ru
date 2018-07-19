---
title: Ошибка компилятора C3175 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3175
dev_langs:
- C++
helpviewer_keywords:
- C3175
ms.assetid: 3f19d513-a05a-4b6c-806f-276fe5c36b90
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 199895ecba509b291d3853f0adabb2b68eee1e49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246407"
---
# <a name="compiler-error-c3175"></a>Ошибка компилятора C3175
«функция1»: невозможно вызвать метод управляемого типа из неуправляемой функции «функция2»  
  
 Неуправляемые функции не может вызывать функции-члены управляемого класса.  
  
 Следующий пример приводит к возникновению ошибки C3175:  
  
```  
// C3175_2.cpp  
// compile with: /clr  
  
ref struct A {  
   static void func() {  
   }  
};  
  
#pragma unmanaged   // remove this line to resolve  
  
void func2() {  
   A::func();   // C3175  
}  
  
#pragma managed  
  
int main() {  
   A ^a = gcnew A;  
   func2();  
}  
```  
