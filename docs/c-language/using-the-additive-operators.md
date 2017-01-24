---
title: "Использование операторов сложения | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "аддитивные операторы"
  - "операторы [C++], сложение"
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование операторов сложения
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующих примерах, иллюстрирующих операторы сложения и вычитания, используются следующие объявления.  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Эти операторы эквивалентны.  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 Значение `i` умножается на длину типа **float** и добавляется в `&x[4]`.  Результирующее значение указателя является адресом `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 В этом примере адрес третьего элемента `x` \(заданного `x[i–2]`\) вычитается из адреса пятого элемента `x` \(заданного `x[i]`\).  Разница делится на длину типа **float**; результатом является целочисленное значение 2.  
  
## См. также  
 [Аддитивные операторы в C](../c-language/c-additive-operators.md)