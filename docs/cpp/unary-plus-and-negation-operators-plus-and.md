---
title: 'Унарный плюс и отрицания: + и - | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8211cf9ebef808ad428e4c94ba97c6bcd22897ea
ms.sourcegitcommit: cdd4808dcb274bbb29618286df4d1d4acd35b9bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2018
---
# <a name="unary-plus-and-negation-operators--and--"></a>Унарные операторы «плюс» и «отрицание»: + и -
## <a name="syntax"></a>Синтаксис  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
```  
  
## <a name="-operator"></a>+ - оператор  
 Результатом унарного оператора сложения (**+**) является значение операнда. Операнд оператора унарного оператора сложения должен иметь арифметический тип.  
  
 Над целочисленными операндами выполняется восходящее приведение целого типа. Результирующим типом является тип, до которого повышается уровень операнда. Таким образом, выражение `+ch`, где `ch` имеет тип `char`, приводит к его к типу `int`; значение не меняется. В разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.  
  
## <a name="--operator"></a>- - оператор  
 Оператор унарного отрицания (**-**) создает отрицательную форму своего операнда. Операнд оператора унарного отрицания должен быть арифметическим типом.  
  
 Над целочисленными операндами выполняется восходящее приведение целого типа, и результирующим типом является тип, до которого повышается уровень операнда. В разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.  
  
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Унарное отрицание величин без знака выполняется путем вычитания значения операнда из числа 2^n, где n — количество битов в объекте заданного типа без знака.
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
