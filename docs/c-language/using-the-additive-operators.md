---
title: "Использование операторов сложения | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C++], addition
- additive operators
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94e2a63412e4fecd5f358659cc4bf02f90df57ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-the-additive-operators"></a>Использование операторов сложения
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
  
 Значение `i` умножается на длину типа **float** и добавляется к `&x[4]`. Результирующее значение указателя является адресом `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 В этом примере адрес третьего элемента `x` (заданного `x[i-2]`) вычитается из адреса пятого элемента `x` (заданного `x[i]`). Разница делится на длину типа **float**; результатом является целочисленное значение 2.  
  
## <a name="see-also"></a>См. также  
 [Аддитивные операторы в C](../c-language/c-additive-operators.md)