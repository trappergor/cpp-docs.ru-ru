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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 16c62e48a0190096e04dc4ccf0c17ca66c2f4094
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3379"></a>Ошибка компилятора C3379
«класс»: вложенный класс не может иметь спецификатор доступа сборки как часть объявления  
  
 При применении к управляемого типа, например класса или структуры, [открытый](../../cpp/public-cpp.md) и [частного](../../cpp/private-cpp.md) означают возможность предоставления класса посредством метаданных сборки. `public`или `private` не может применяться к вложенному классу, уровень доступа сборки, включающего класса.  
  
 При использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), `ref` и `value` означают, что класс является управляемым (см. [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
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

