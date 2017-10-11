---
title: "Предупреждение компилятора C4484 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 06246c811c59ff126cd61d5c10d0d30a68857c2c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4484"></a>Предупреждение компилятора C4484
«переопределяющая_функция»: соответствует методу базового класса «базового класса», но не помечен «virtual», «new» или «override»; предполагается «new» (а не «virtual»)  
  
 При компиляции с параметром **/CLR**, компилятор не переопределяет неявно функцию базового класса, это означает, что функция получит новую ячейку в таблице vtable. Чтобы устранить, явно укажите, является ли функция переопределения.  
  
 Дополнительные сведения:  
  
-   [/ CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [New (новый слот в vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 всегда выдается как ошибка. Используйте [предупреждение](../../preprocessor/warning.md) pragma, чтобы отключить предупреждение C4484.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4484.  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```
