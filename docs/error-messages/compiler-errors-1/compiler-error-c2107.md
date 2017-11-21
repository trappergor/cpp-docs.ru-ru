---
title: "Ошибка компилятора C2107 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2107
dev_langs: C++
helpviewer_keywords: C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72ae821ce05d978f2f520b86f5a63b2e4569aabc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2107"></a>Ошибка компилятора C2107
Недопустимый индекс, косвенное обращение не разрешено  
  
 Индекс применяется к выражению, результатом вычисления не указатель.  
  
## <a name="example"></a>Пример  
 C2107 может возникать в результате неправильного использования `this` указатель типа значения для доступа к индексатору по умолчанию этого типа. Дополнительные сведения см. в разделе [семантика этого указателя](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 Следующий пример приводит к возникновению ошибки C2107.  
  
```  
// C2107.cpp  
// compile with: /clr  
using namespace System;  
  
value struct B {  
   property String ^ default[String ^] {  
      String ^ get(String ^ data) {  
         return "abc";  
      }  
   }  
   void Test() {  
      Console::WriteLine("{0}", this["aa"]);   // C2107  
      Console::WriteLine("{0}", this->default["aa"]);   // OK  
   }  
};  
  
int main() {  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```