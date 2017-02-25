---
title: "Предупреждение компилятора C4484 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4484"
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора C4484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переопределяющая\_функция": соответствует методу ссылочного базового класса "функция\_базового\_класса", но не помечена как "виртуальная", "новая" или "переопределяющая"; предполагается "новая" \(а не "виртуальная"\)  
  
 При компиляции с помощью параметра **\/clr** компилятор не переопределяет неявно функцию базового класса, что означает, что функция получит новую ячейку в виртуальной таблице.  Для решения проблемы укажите явно, нужно ли переопределить функцию.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new \(новый слот в vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 Предупреждение C4484 всегда выводится в качестве ошибки.  Используйте директиву pragma [warning](../../preprocessor/warning.md), чтобы отключить предупреждение C4484.  
  
## Пример  
 В следующем примере показано возникновение ошибки C4484.  
  
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