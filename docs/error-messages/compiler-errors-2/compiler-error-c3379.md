---
title: "Ошибка компилятора C3379 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e6fa111a525d81c418d3285c05af86b700e8cb08
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3379"></a>Ошибка компилятора C3379
«класс»: вложенный класс не может иметь спецификатор уровня доступа сборки как часть объявления  
  
 При применении к управляемому типу, например класса или структуры, [открытый](../../cpp/public-cpp.md) и [закрытый](../../cpp/private-cpp.md) означают возможность предоставления класса посредством метаданных сборки. `public`или `private` не может применяться к вложенному классу, уровень доступа сборки, включающего класса.  
  
 При использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), `ref` и `value` означают, что управляемый класс (в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 Следующий пример приводит к возникновению ошибки C3379:  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  

