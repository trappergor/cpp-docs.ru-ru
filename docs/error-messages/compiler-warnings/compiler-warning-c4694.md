---
title: "Предупреждение компилятора C4694 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4694"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4694"
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Предупреждение компилятора C4694
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"class\_1": у запечатанного абстрактного класса не может быть базового класса "базовый\_класс"  
  
 Абстрактный и запечатанный класс не может наследовать от ссылочного типа; запечатанный и абстрактный класс не может ни реализовывать функции базового класса, ни разрешать использовать себя в качестве базового класса.  
  
 Дополнительные сведения см. в разделах [abstract](../../windows/abstract-cpp-component-extensions.md), [запечатанные](../../windows/sealed-cpp-component-extensions.md) и [Классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4694.  
  
```  
// C4694.cpp // compile with: /c /clr ref struct A {}; ref struct B sealed abstract : A {};   // C4694  
```