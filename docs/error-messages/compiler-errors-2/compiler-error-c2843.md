---
title: "Ошибка компилятора C2843 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2843
dev_langs:
- C++
helpviewer_keywords:
- C2843
ms.assetid: 9d3f2ac4-eea5-4fed-abeb-e752f442bfcc
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1c5e73c80fcb816a54d4bc815e68471282c59d59
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2843"></a>Ошибка компилятора C2843
member: невозможно получить адрес нестатических данных-члена или метода управляемого типа или типа WinRT  
  
 Экземпляр необходим, чтобы получить адрес нестатических элементов данных управляемого типа класса или интерфейса и класса или интерфейса WinRT.  
  
 В следующем примере показано возникновение ошибки C2843 и приводятся сведения по ее устранению.  
  
```  
// C2843_2.cpp  
// compile with: /clr  
public ref class C {  
public:  
   int m_i;  
};  
  
ref struct MyStruct {  
   static void sf() {}  
   void f() {}  
};  
  
int main() {  
   MyStruct ^ps = gcnew MyStruct;  
   void (__clrcall MyStruct::*F1)() = & MyStruct::f;   // C2843  
   void (__clrcall MyStruct::*F2)() = & ps->f;   // C2843  
   void (__clrcall MyStruct::*F3)();   // C2843  
  
   void (__clrcall *F5)() = MyStruct::sf;   // OK  
   void (__clrcall *F6)() = & ps->sf;   // OK  
  
   interior_ptr<int> i = &C::m_i; // C2843  
   C ^x = gcnew C();  
   interior_ptr<int> ii = &x->m_i;  
}  
```  

