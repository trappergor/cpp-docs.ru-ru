---
title: "Ошибка компилятора C3642 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3642
dev_langs:
- C++
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3dace0204f4534ee630924bd443d028efc2afc14
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3642"></a>Ошибка компилятора C3642
«return_type/args»: невозможно вызвать функцию с соглашением вызова из машинного кода __clrcall  
  
 Функция, которая отмечена [__clrcall](../../cpp/clrcall.md) соглашение о вызовах не может вызываться из машинного (неуправляемого) кода.  
  
 *return_type/args* либо имя функции или тип `__clrcall` попытка вызова функции.  Тип используется при вызове через указатель функции.  
  
 Чтобы вызвать управляемую функцию из собственного контекста, можно добавить функцию оболочки, которая вызовет `__clrcall` функции. Или можно использовать механизм маршалинга среды CLR; в разделе [как: маршалирование функция указатели с помощью PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению ошибки C3642:  
  
```  
// C3642.cpp  
// compile with: /clr  
using namespace System;  
struct S {  
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall  
      Console::WriteLine(s);  
   }  
   void Test2(char * s) {  
      Test(gcnew String(s));  
   }  
};  
  
#pragma unmanaged  
int main() {  
   S s;  
   s.Test("abc");   // C3642  
   s.Test2("abc");   // OK  
}  
```