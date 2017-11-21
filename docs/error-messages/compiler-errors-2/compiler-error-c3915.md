---
title: "Ошибка компилятора C3915 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3915
dev_langs: C++
helpviewer_keywords: C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b753abc02e84c8373fe6115a5bf2f2a0719094f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3915"></a>Ошибка компилятора C3915
«тип» имеет не индексированное свойство по умолчанию (индексатора класса)  
  
 Тип не имеет по умолчанию, индексированного свойства.  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3915.  
  
```  
// C3915.cpp  
// compile with: /clr  
ref class X {  
public:  
// uncomment property to resolve this C3915  
//   property int default[]  
//   {  
//      int get(int i)  
//      {  
//         return 863;  
//      }  
//   }  
};  
  
int main() {  
   X^ x = new X;  
   System::Console::WriteLine(x[1]);   // C3915  
}  
```  
  
## <a name="example"></a>Пример  
 C3915 также может возникать при попытке использовать индексатор по умолчанию в той же единице компиляции, в котором он был определен с <xref:System.Reflection.DefaultMemberAttribute>.  
  
 Следующий пример приводит к возникновению ошибки C3915.  
  
```  
// C3915_b.cpp  
// compile with: /clr  
using namespace System;  
  
[Reflection::DefaultMember("XXX")]  
ref struct A {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
ref struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
   Console::WriteLine("{0}", mya[3]);   // C3915  
  
   B ^ myb = gcnew B();  
   Console::WriteLine("{0}", myb[3]);   // OK  
}  
```