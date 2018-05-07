---
title: Предупреждение компилятора C4484 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 75531c207f0136f16109b4d69d689b883998aae2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4484"></a>Предупреждение компилятора C4484
«переопределяющая_функция»: соответствует методу базового класса «базового класса», но не помечен «virtual», «new» или «override»; предполагается «new» (а не «virtual»)  
  
 При компиляции с параметром **/CLR**, компилятор не переопределяет неявно функцию базового класса, это означает, что функция получит новую ячейку в таблице vtable. Чтобы устранить, явно укажите, является ли функция переопределения.  
  
 Дополнительные сведения:  
  
-   [/clr (компиляция среды выполнения)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
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