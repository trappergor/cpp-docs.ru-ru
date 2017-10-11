---
title: "Ошибка компилятора C3203 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3203
dev_langs:
- C++
helpviewer_keywords:
- C3203
ms.assetid: 6356770e-22c1-434c-91fe-f60b0aa23b91
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: eb8a9272a62080bd567989d90502d0ca2d003a57
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3203"></a>Ошибка компилятора C3203
type: неспециализированный шаблон класса нельзя использовать в качестве аргумента шаблона или универсального аргумента для шаблонного или универсального параметра param, требуется действительный тип  
  
 Шаблонному или универсальному классу передан недопустимый аргумент. Шаблонный или универсальный класс ожидает тип в качестве параметра.  
  
 Эта ошибка может возникать в результате действий по обеспечению совместимости компилятора с Visual C++ 2005: шаблон неспециализированного класса нельзя использовать в качестве аргумента шаблона в списке базовых классов. Для устранения ошибки C3203 следует явным образом добавить параметры типов в имя класса шаблона при использовании его в качестве параметра шаблона в списке базовых классов.  
  
```  
// C3203.cpp  
template< typename T >  
struct X {  
   void f(X) {}  
};  
  
template< typename T >  
struct Y : public X<Y> {   // C3203  
// try the following line instead  
// struct Y : public X<Y<T> > {  
   void f(Y) {}  
};  
  
int main() {  
   Y<int> y;  
}  
```  
  
 В следующем примере показано возникновение ошибки C3203 и приводятся сведения по ее устранению.  
  
```  
// C3203_b.cpp  
// compile with: /c  
template <class T>  
struct S1 {};  
  
template <class T>  
class C1 {};  
  
typedef C1<S1> MyC1;   // C3203  
  
// OK  
template <template <class> class T>  
class C2 {};  
  
typedef C2<S1> MyC1;  
  
template <class T>  
class C3 {};  
  
typedef C3<S1<int> > MyC12;  
```  
  
 Ошибка C3203 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C3203_c.cpp  
// compile with: /clr /c  
generic <class T>  
value struct GS1 {};  
  
generic <class T>  
value struct GC1 {};  
  
typedef GC1<GS1> MyGC1;   // C3203  
typedef GC1<GS1<int> > MyGC2;   // OK  
```
