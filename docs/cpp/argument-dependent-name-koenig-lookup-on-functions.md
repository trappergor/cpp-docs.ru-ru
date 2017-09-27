---
title: "Поиск имени с зависимостью от аргументов (поиск Koenig) функций | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a27b75a8be6b250e27a667a8aebf4e399fdd3f1f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>Поиск имен функций с зависимостью от аргументов (поиск Koenig)
Компилятор может использовать поиск имени с зависимостью от аргументов для поиска определения неопределенного вызова функции. Поиск имени с зависимостью от аргументов также называется поиском Koenig. Тип каждого аргумента в вызове функции определяется в иерархии пространств имен, классов, структур, объединений или шаблонов. При указании неопределенного [постфиксные](../cpp/postfix-expressions.md) вызов функции, компилятор выполняет поиск определения функции в иерархии, связанной с каждым типом аргумента.  
  
## <a name="example"></a>Пример  
 В образце компилятор замечает, что функция `f()` принимает аргумент `x`. Аргумент `x` принадлежит типу `A::X`, определенному в пространстве имен `A`. Компилятор выполняет поиск пространства имен `A` и обнаруживает определение функции `f()`, принимающей аргумент типа `A::X`.  
  
```  
// argument_dependent_name_koenig_lookup_on_functions.cpp  
namespace A  
{  
   struct X  
   {  
   };  
   void f(const X&)  
   {  
   }  
}  
int main()  
{  
// The compiler finds A::f() in namespace A, which is where   
// the type of argument x is defined. The type of x is A::X.  
   A::X x;  
   f(x);     
}  
```  

