---
title: "virtual (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "virtual_cpp"
  - "virtual"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "базовые классы, виртуальные"
  - "виртуальные базовые классы, объявление"
  - "виртуальные функции, объявление"
  - "virtual - ключевое слово [C++]"
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# virtual (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ключевое слово `virtual` объявляет виртуальную функцию или виртуальный базовый класс.  
  
## Синтаксис  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### Параметры  
 `type-specifiers`  
 Указывает возвращаемый тип виртуальной функции\-члена.  
  
 `member-function-declarator`  
 Объявляет функцию\-член.  
  
 `access-specifier`  
 Определяет уровень доступа к базовому классу: `public` \(открытый\), `protected` \(защищенный\) или `private` \(закрытый\).  Может находиться перед ключевым словом `virtual` или после него.  
  
 `base-class-name`  
 Определяет ранее объявленный тип класса.  
  
## Заметки  
 Дополнительные сведения см. в разделах [Виртуальные функции](../cpp/virtual-functions.md) и [Виртуальные базовые классы](../Topic/Virtual%20Base%20Classes.md).  
  
 Кроме того, см. разделы, посвященные следующим ключевым словам: [class](../cpp/class-cpp.md), [private](../Topic/private%20\(C++\).md), [public](../cpp/public-cpp.md) и [protected](../Topic/protected%20\(C++\).md).  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)