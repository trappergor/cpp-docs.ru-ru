---
title: "Ошибка C3206 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3206
dev_langs:
- C++
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 69e6fcd77916af3defc29dfb12381d3491e478e6
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3206"></a>Ошибка компилятора C3206
"функция": недопустимый аргумент типа для "параметр", отсутствует список аргументов типа для типа класса "имя_типа"  
  
 Функция-шаблон определена как принимающая аргумент типа шаблона. Однако передан аргумент шаблона template.  
  
 Следующий пример приводит к возникновению ошибки C3206:  
  
```  
// C3206.cpp  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S>();   // C3206  
   // try the following line instead  
   // f<S<int> >();  
}  
```  
  
 Возможное решение  
  
```  
// C3206b.cpp  
// compile with: /c  
template <class T>  
void f() {}  
  
template <class T>  
struct S {};  
  
void f1() {  
   f<S<int> >();  
}  
```  
  
 Ошибка C3206 также может возникнуть при использовании универсальных шаблонов.  
  
```  
// C3206c.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS>();   // C3206  
}  
```  
  
 Возможное решение  
  
```  
// C3206d.cpp  
// compile with: /clr  
generic <class GT1>  
void gf() {}  
  
generic <class T>  
value struct GS {};  
  
int main() {  
   gf<GS<int> >();  
}  
```  
  
 Эта ошибка может возникнуть и в результате действий по обеспечению совместимости компилятора с Visual C++ .NET 2003, где шаблоны класса недопустимы в качестве аргументов типа шаблона.  
  
 Шаблон класса недопустим в качестве аргумента типа шаблона. Это работало в Visual C++ .NET 2003, но недопустимо в C++.  
  
 Приведенный ниже пример компилируется в Visual C++ .NET 2002, но его компиляция в Visual C++ .NET 2003 завершается неудачей.  
  
```  
// C3206e.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T<int> t;  
}  
  
int main() {  
   func<S>();   // C3206 S is not a type.  
}  
```  
  
 Возможное решение  
  
```  
// C3206f.cpp  
template <class T>  
struct S {};  
  
template <class T>  
void func() {   // takes a type  
   T t;  
}  
  
int main() {  
   func<S<int> >();  
}  
```  
  
 Если параметр шаблона template необходим, то способ устранения ошибки, работающий в обеих версиях (Visual C++ .NET 2003 и Visual C++ .NET 2002), требует, чтобы функция была заключена в класс шаблона, принимающий параметр шаблона template.  
  
```  
// C3206g.cpp  
template <class T>  
struct S {};  
  
template<template<class> class TT>  
struct X {  
   static void func() {  
      TT<int> t1;  
      TT<char> t2;  
   }  
};  
  
int main() {  
   X<S>::func();  
}  
```
