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
ms.openlocfilehash: 9f2bdbc6a22754587dce3cb2a4c9b2baf12a1a1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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