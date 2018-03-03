---
title: "Ошибка компилятора C2477 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2477
dev_langs:
- C++
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28cdd86ac20ed1c519905f7908e8b4a1d34cf6f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2477"></a>Ошибка компилятора C2477
«член»: не удается инициализировать статические данные-член в производном классе  
  
 Статические данные-член шаблона класса был инициализирован неправильно. Это критическое изменение в версии компилятора Visual C++ до Visual Studio .NET 2003, в целях обеспечения соответствия стандарту ISO c++.  
  
 Следующий пример приводит к возникновению ошибки C2477:  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```