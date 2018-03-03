---
title: "Ошибка компилятора C3367 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e341266c37411d96a4cf313e6a101e48aeb2a85d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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