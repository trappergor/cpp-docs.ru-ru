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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa5f209dd3a77bcc4ec3c21d589fb8ba1ed3faf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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