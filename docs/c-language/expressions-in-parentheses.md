---
title: "Выражения в скобках | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parentheses
- expression evaluation, evaluation order
- expressions [C++], evaluating
- parentheses, expressions
ms.assetid: b8636147-6982-408c-9e64-29e40678ee43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c09209a323a06f883a54e7ecaec17c55a3bc6205
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-parentheses"></a>Выражения в скобках
Любой операнд можно заключить в круглые скобки без изменения типа или значения заключенного в скобки выражения. Например, в выражении  
  
```  
( 10 + 5 ) / 5  
```  
  
 скобки вокруг `10 + 5` означают, что значение `10 + 5` вычисляется первым и становится левым операндом для оператора деления (**/**). Результат выражения `( 10 + 5 ) / 5` — 3. Без скобок результатом выражения `10 + 5 / 5` было бы значение 11.  
  
 Хотя круглые скобки влияют на группировку операндов в выражении, они не могут гарантировать определенный порядок вычисления во всех случаях. Например, ни скобки, ни группировка слева направо в следующем выражении не гарантируют, что значение `i` будет находиться в какой-либо из частей выражения.  
  
```  
( i++ +1 ) * ( 2 + i )  
```  
  
 Компилятор может вычислить две части умножения в любом порядке. Если начальное значение `i` равно нулю, то все выражение может быть вычислено как один из двух следующих операторов.  
  
```  
( 0 + 1 + 1 ) * ( 2 + 1 )   
( 0 + 1 + 1 ) * ( 2 + 0 )  
```  
  
 Описание исключений, возникающих в результате побочных эффектов, см. в статье [Побочные эффекты](../c-language/side-effects.md).  
  
## <a name="see-also"></a>См. также  
 [Первичные выражения в C](../c-language/c-primary-expressions.md)