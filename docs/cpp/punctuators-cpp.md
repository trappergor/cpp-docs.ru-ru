---
title: "Знаки препинания C++ | Microsoft Docs"
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
  - ";"
  - ","
  - "{"
  - "}"
  - "("
  - ")"
  - "["
  - "]"
  - "!"
  - "%"
  - "^"
  - "*"
  - """
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "знаки препинания"
ms.assetid: 1521564c-a977-488a-9490-068079897592
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Знаки препинания C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Символы пунктуации в C\+\+ имеют синтаксическое и семантическое значение для компилятора, однако сами по себе не указывают на операцию, которая позволяет получить значение.  Некоторые символы пунктуации \(по отдельности или в сочетании\) могут также быть операторами C\+\+ или иметь значение для препроцессора.  
  
 К символам пунктуации относятся следующие:  
  
```  
! % ^ & * ( ) – + = { } | ~  
[ ] \ ; ' : " < > ? , . / #  
```  
  
 После [этапа преобразования](../preprocessor/phases-of-translation.md) 4 символы пунктуации **\[ \]**, **\( \)** и **{ }** должны располагаться попарно.  
  
## См. также  
 [Лексические соглашения](../cpp/lexical-conventions.md)