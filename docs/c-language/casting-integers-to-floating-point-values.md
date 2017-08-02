---
title: "Приведение целочисленных значений к значениям с плавающей запятой | Документация Майкрософт"
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
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 5635ddf0e940e1f374bfd97d7d6f53dc1b57daec
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="casting-integers-to-floating-point-values"></a>Приведение целочисленных значений к значениям с плавающей запятой
**ANSI 3.2.1.3** Направление усечения при преобразовании целого числа в число с плавающей запятой, которое не может точно представить исходное значение  
  
 Если целое число приводится к значению с плавающей запятой, которое точно не может представить это значение, это значение округляется (в большую или меньшую сторону) до ближайшего подходящего значения.  
  
 Например, приведение числа типа **unsigned long** (точность — 32 бита) к числу типа **float** (мантисса которого имеет точность 23 бита) приводит к округлению числа до ближайшего кратного 256. Значения **long** в диапазоне от 4 294 966 913 до 4 294 967 167 округляются до значения 4 294 967 040 с типом **float**.  
  
## <a name="see-also"></a>См. также  
 [Вычисления с плавающей запятой](../c-language/floating-point-math.md)
