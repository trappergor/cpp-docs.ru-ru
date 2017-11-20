---
title: "Приведение целочисленных значений к значениям с плавающей запятой | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0c91c9533baec350ba66ae1ab4db472c0ea8bcdf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="casting-integers-to-floating-point-values"></a>Приведение целочисленных значений к значениям с плавающей запятой
**ANSI 3.2.1.3** Направление усечения при преобразовании целого числа в число с плавающей запятой, которое не может точно представить исходное значение  
  
 Если целое число приводится к значению с плавающей запятой, которое точно не может представить это значение, это значение округляется (в большую или меньшую сторону) до ближайшего подходящего значения.  
  
 Например, приведение числа типа **unsigned long** (точность — 32 бита) к числу типа **float** (мантисса которого имеет точность 23 бита) приводит к округлению числа до ближайшего кратного 256. Значения **long** в диапазоне от 4 294 966 913 до 4 294 967 167 округляются до значения 4 294 967 040 с типом **float**.  
  
## <a name="see-also"></a>См. также  
 [Вычисления с плавающей запятой](../c-language/floating-point-math.md)