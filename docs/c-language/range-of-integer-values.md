---
title: "Диапазон целочисленных значений | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 568bc2884f7fb9642175a006c09a218d8cbe1668
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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