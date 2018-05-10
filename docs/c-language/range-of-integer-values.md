---
title: Диапазон целочисленных значений | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2695b5d2a006529042453b7048bec400388fb74b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="range-of-integer-values"></a>Диапазон целочисленных значений
**ANSI 3.1.2.5** Представления и наборы значений различных целочисленных типов данных  
  
 Целочисленные типы данных содержат 32 бита (4 байта). Знаковые целочисленные типы представлены в форме дополнительного кода. В старшем разряде содержится знак: 1 означает отрицательные числа, 0 — положительные числа и ноль. Значения перечислены ниже:  
  
|Тип|Минимальное и максимальное значение|  
|----------|-------------------------|  
|**unsigned short**|От 0 до 65535|  
|`signed short`|От -32768 до 32767|  
|`unsigned long`|От 0 до 4294967295|  
|**signed long**|От -2147483648 до 2147483647|  
  
## <a name="see-also"></a>См. также  
 [Целые числа](../c-language/integers.md)