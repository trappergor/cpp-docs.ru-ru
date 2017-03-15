---
title: "bool (C++) | Microsoft Docs"
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
  - "bool_cpp"
  - "bool"
  - "__BOOL_DEFINED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__BOOL_DEFINED - макрос"
  - "bool - ключевое слово [C++]"
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bool (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Это ключевое слово является встроенным типом.  Переменная данного типа может иметь значения [true](../cpp/true-cpp.md) и [false](../Topic/false%20\(C++\).md).  Условные выражения имеют тип `bool`, и поэтому имеют значения типа `bool`.  Например, `i!=0` теперь имеет значение **true** или **false** в зависимости от значения `i`.  
  
 Значения **true** и **false** находятся в следующих отношениях.  
  
```  
!false == true  
!true == false  
```  
  
 В следующем операторе  
  
```  
if (condexpr1) statement1;   
```  
  
 Если значение `condexpr1` равно **true**, то `statement1` выполняется всегда; если значение `condexpr1` равно **false**, то `statement1` не выполняется никогда.  
  
 Если постфиксный или префиксный оператор `++` применяется к переменной типа `bool`, переменная принимает значение **true**.  Постфиксный или префиксный оператор `--` невозможно применить к переменной этого типа.  
  
 Тип `bool` участвует в восходящем приведении целого типа.  R\-значение типа `bool` можно преобразовать в r\-значение типа `int`, при этом значение **false** становится нулем, а значение **true** — единицей.  Как отдельный тип `bool` участвует в разрешении перегрузки.  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Фундаментальные типы](../cpp/fundamental-types-cpp.md)