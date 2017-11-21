---
title: "Ошибка компилятора C3918 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3918
dev_langs: C++
helpviewer_keywords: C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bf9cf676cf7435eaf1f0b924fbadcaddef842b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3918"></a>Ошибка компилятора C3918
«член» член данных требует использования  
  
 Ошибка C3918 может возникать по нескольким причинам, связанным с событиями.  
  
## <a name="example"></a>Пример  
 C3918 может возникать, если в текущем контексте требуется член класса. Следующий пример приводит к возникновению ошибки C3918.  
  
```  
// C3918.cpp  
// compile with: /clr /c  
public ref class C {  
public:  
   System::Object ^ o;  
   delegate void Del();  
  
   event Del^ MyEvent {  
      void add(Del^ev) {  
         if ( MyEvent != nullptr) {}   // C3918  
         if ( o != nullptr) {}   // OK  
   }  
   void remove(Del^){}  
   }  
};  
```  
  
## <a name="example"></a>Пример  
 C3918 также может возникать при попытке проверки тривиального события со значением NULL (имя события более не будет предоставлять прямой доступ к делегату резервного хранилища для события).  
  
 Следующий пример приводит к возникновению ошибки C3918.  
  
```  
// C3918_2.cpp  
// compile with: /clr /c  
using namespace System;  
public delegate int MyDel(int);  
  
interface struct IEFace {  
   event MyDel ^ E;  
};  
  
ref struct EventSource : public IEFace {  
   virtual event MyDel ^ E;  
   void Fire_E(int i) {  
      if (E)   // C3918  
         E(i);  
   }  
};  
```  
  
## <a name="example"></a>Пример  
 Ошибка C3918 также может возникать, если неправильно подписаться на событие. Следующий пример приводит к возникновению ошибки C3918.  
  
```  
// C3918_3.cpp  
// compile with: /clr /c  
using namespace System;  
  
public delegate void del();  
  
public ref class A {  
public:  
   event del^ e {  
      void add(del ^handler ) {  
         d += handler;  
      }  
  
      void remove(del ^handler) {  
         d -= handler;  
      }  
  
      void raise() {   
         d();  
      }  
   }  
  
   del^ d;  
   void f() {}  
  
   A() {  
      e = gcnew del(this, &A::f);   // C3918  
      // try the following line instead  
      // e += gcnew del(this, &A::f);  
      e();  
   }  
};  
  
int main() {  
   A a;  
}  
```