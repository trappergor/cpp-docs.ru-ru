---
title: Ошибка компилятора C3367 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2884e38d1ad1aecef8e7b0723674ebd9849d8f40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3367"></a>Ошибка компилятора C3367
"функция_статического_члена": невозможно использовать статическую функцию для создания несвязанного делегата  
  
При вызове несвязанного делегата необходимо передать экземпляр объекта. Так как статическая функция-член вызывается через имя класса, с помощью функции-члена экземпляра можно создать только несвязанный делегат.  
  
Дополнительные сведения о несвязанные делегаты см. в разделе [как: определение и использование делегатов (C + +/ CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3367.  
  
```cpp  
// C3367.cpp  
// compile with: /clr  
ref struct R {  
   void b() {}  
   static void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::b);   // OK  
   Del ^ b = gcnew Del(&R::f);   // C3367  
}  
```