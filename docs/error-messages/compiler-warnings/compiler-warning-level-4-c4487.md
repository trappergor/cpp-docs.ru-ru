---
title: "Предупреждение (уровень 4) C4487 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4487
dev_langs: C++
helpviewer_keywords: C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4c992385c9bd2a7f2c918956ba128ea45afa0752
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4487"></a>Предупреждение компилятора (уровень 4) C4487
«невиртуальному»: соответствует наследуемые невиртуальному методу «базового класса», но не помечен явно «new»  
  
 Функция в производном классе имеет ту же сигнатуру, как функция невиртуальный базовый класс. C4487 напоминает, что функция производного класса не переопределяет функцию базового класса. Явно Определите функцию производного класса, как `new` Чтобы устранить это предупреждение.  
  
 Дополнительные сведения см. в разделе [new (новый слот в vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4487.  
  
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