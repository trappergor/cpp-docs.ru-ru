---
title: "Ошибка компилятора C2797 | Microsoft Docs"
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
  - "C2797"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2797"
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2797
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инициализация списка внутри списка инициализатора членов или инициализатора членов нестатических данных не выполнена.  
  
 Компилятор C\+\+ в Visual Studio не выполняет инициализацию списков внутри инициализатора членов или инициализатора членов нестатических данных.  До Visual Studio 2013 Update 3 в таких случаях инициализация автоматически преобразовывалась в вызов функции, что могло приводить к получению неверного кода.  В Visual Studio 2013 Update 3 в таких случаях выводится ошибка.  
  
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
  
 Чтобы устранить эту проблему, используйте явное создание внутренних списков.  Например:  
  
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
  
 \(Компилятор в Visual Studio 2013 делает это неявным образом во всех версиях до Visual Studio 2013 Update 3.\)