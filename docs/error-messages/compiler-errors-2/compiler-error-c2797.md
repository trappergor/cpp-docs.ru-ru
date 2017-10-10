---
title: "Ошибка компилятора C2797 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 09c5a26a1a7bb594419d2db211f86074d01da84e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2797"></a>Ошибка компилятора C2797
(Устарело) Инициализация списка внутри списка инициализаторов членов или инициализатора члена нестатических данных не реализован.  
  
 Это предупреждение не используется в Visual Studio 2015. В Visual Studio 2013 и более ранних версий компилятор Visual C++ не реализует инициализация списка внутри списка инициализатора членов или инициализатор члена нестатических данных. До Visual Studio 2013 Update 3 в таких случаях инициализация автоматически преобразовывалась в вызов функции, что могло приводить к получению неверного кода. В Visual Studio 2013 Update 3 в таких случаях выводится ошибка.  
  
 Этот пример создает C2797:  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 Этот пример также создает C2797:  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 Чтобы устранить эту проблему, используйте явное создание внутренних списков. Например:  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 Если инициализация списка не требуется:  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 (Компилятор в Visual Studio 2013 делает это неявным образом во всех версиях до Visual Studio 2013 Update 3.)
