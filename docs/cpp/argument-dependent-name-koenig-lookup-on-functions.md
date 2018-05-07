---
title: Поиск имени с зависимостью от аргументов (поиск Koenig) функций | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6a06140522f9d4074eaa0403d0d05fe0f79adec0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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
