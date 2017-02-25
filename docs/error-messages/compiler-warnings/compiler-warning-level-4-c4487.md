---
title: "Предупреждение компилятора (уровень 4) C4487 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4487"
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Предупреждение компилятора (уровень 4) C4487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция производного класса": соответствует унаследованному невиртуальному методу "функция базового класса", но не помечен явно как "new"  
  
 Сигнатура функции производного класса совпадает с сигнатурой невиртуальной функции базового класса.  Предупреждение C4487 свидетельствует о том, что функция производного класса не переопределяет функцию базового.  Чтобы устранить это предупреждение, явно определите функцию производного класса с помощью ключевого слова `new`.  
  
 Для получения дополнительной информации см. [new \(новый слот в vtable\)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере возникает предупреждение C4487.  
  
```  
// C4487.cpp  
// compile with: /W4 /clr  
using namespace System;  
public ref struct B {  
   void f() { Console::WriteLine("in B::f"); }  
   void g() { Console::WriteLine("in B::g"); }  
};  
  
public ref struct D : B {  
   void f() { Console::WriteLine("in D::f"); }   // C4487  
   void g() new { Console::WriteLine("in D::g"); }   // OK  
};  
  
int main() {  
   B ^ a = gcnew D;  
   // will call base class functions  
   a->f();  
   a->g();  
}  
```