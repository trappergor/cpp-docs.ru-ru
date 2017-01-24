---
title: "Ошибка компилятора C2676 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2676"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2676"
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2676
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

бинарный "оператор": "тип" не определяет этот оператор или преобразование к типу приемлемо к встроенному оператору  
  
 Чтобы использовать оператор, необходимо перегрузить его для указанного типа или определить преобразование в тип, для которого определен оператор.  
  
## Пример  
 В следующем примере возникает ошибка C2676.  
  
```  
// C2676.cpp  
// C2676 expected  
struct C {  
   C();  
} c;  
  
struct D {  
   D();  
   D operator >>( C& ){return * new D;}  
   D operator <<( C& ){return * new D;}  
} d;  
  
struct E {  
   // operator int();  
};  
  
int main() {  
   d >> c;  
   d << c;  
   E e1, e2;  
   e1 == e2;   // uncomment operator int in class E, then  
               // it is OK even though neither E::operator==(E) nor   
               // operator==(E, E) defined. Uses the conversion to int   
               // and then the builtin-operator==(int, int)  
}  
```  
  
## Пример  
 Ошибка C2676 также может возникнуть при попытке создания арифметического указателя на базе указателя `this` ссылочного типа.  
  
 Указатель `this` ссылочного типа представляет собой дескриптор типа.  Дополнительные сведения см. в разделе [Семантика этого указателя](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).  
  
 В следующем примере возникает ошибка C2676.  
  
```  
// C2676_a.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      Console::WriteLine("{0}", this + 3.3);   // C2676  
      Console::WriteLine("{0}", this[3.3]);   // OK  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
}  
```