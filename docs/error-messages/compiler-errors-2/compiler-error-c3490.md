---
title: "Ошибка компилятора C3490 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3490"
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная" не может быть изменен, поскольку доступ к нему осуществляется через константный объект  
  
 Лямбда\-выражение, объявленное в методе `const`, не может изменять данные недоступного для изменения члена.  
  
### Исправление ошибки  
  
-   Удалите модификатор `const` из объявления метода.  
  
## Пример  
 Приведенный ниже пример вызывает ошибку C3490, так как переменная\-член `_i` изменяется в методе `const`.  
  
```  
// C3490a.cpp // compile with: /c class C { void f() const  { auto x = [=]() { _i = 20; }; // C3490 } int _i; };  
```  
  
## Пример  
 В приведенном ниже примере ошибка C3490 устраняется путем удаления модификатора `const` из объявления метода.  
  
```  
// C3490b.cpp // compile with: /c class C { void f() { auto x = [=]() { _i = 20; }; } int _i; };  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)