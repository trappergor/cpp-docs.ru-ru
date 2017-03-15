---
title: "Ошибка компилятора C3915 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3915"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3915"
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3915
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип" не имеет индексированного свойства по умолчанию \(индексатора класса\)  
  
 У типа нет индексированного свойства по умолчанию.  
  
 Дополнительные сведения см. в описании [property](../../windows/property-cpp-component-extensions.md).  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C3915.  
  
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
  
## Пример  
 Также ошибка C3915 может возникать при попытке использовать индексатор по умолчанию в той же единице компиляции, в которой он был определен с атрибутом <xref:System.Reflection.DefaultMemberAttribute>.  
  
 В следующем примере продемонстрировано возникновение ошибки C3915.  
  
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