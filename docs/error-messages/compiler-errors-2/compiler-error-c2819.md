---
title: "Ошибка компилятора C2819 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2819
dev_langs:
- C++
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 770609ed06fd3e123ce02688e3f091018c9f5444
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2819"></a>Ошибка компилятора C2819
Тип «тип» не имеет перегруженный «operator ->»  
  
 Необходимо определить `operator->()` использовать данную операцию над указателями.  
  
 В следующем примере возникает ошибка C2819:  
  
```  
// C2819.cpp  
// compile with: /c  
class A {  
   public:  
      int i;  
};  
  
class B {};  
  
void C(B j) {  
   j->i;   // C2819  
}  
  
class D {  
   A* pA;  
  
   public:  
      A* operator->() {  
         return pA;  
      }  
};  
  
void F(D j) {  
   j->i;  
}  
```  
  
 C2819 также может возникнуть при использовании [семантика стека C++ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md). В следующем примере возникает ошибка C2819:  
  
```  
// C2819_b.cpp  
// compile with: /clr  
ref struct R {  
   void Test() {}  
};  
  
int main() {  
   R r;  
   r->Test();   // C2819  
   r.Test();   // OK  
}  
```
