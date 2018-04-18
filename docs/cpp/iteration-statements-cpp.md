---
title: "Операторы перебора (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c06ae1c043551bbb4ed6469ab3f87d1ed86fd92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iteration-statements-c"></a>Операторы перебора (C++)
Операторы перебора приводят к тому, что операторы (или составные операторы) выполняются ноль или более раз в соответствии с некоторыми критериями завершения цикла. Если эти операторы являются составными операторами, они выполняются по порядку, за исключением случаев либо инструкции [break](../cpp/break-statement-cpp.md) или инструкции [continue](../cpp/continue-statement-cpp.md).  
  
 В C++ есть четыре оператора перебора — [while](../cpp/while-statement-cpp.md), [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md), и [for для диапазона](../cpp/range-based-for-statement-cpp.md). Каждый из них повторяется пока его выражение завершения не примет значение ноль (false) или цикл не будет принудительно завершен инструкцией **break**. В следующей таблице приведены сводные сведения об этих операторах и их действии. Дополнительные сведения о каждом из них см. в последующих разделах.  
  
### <a name="iteration-statements"></a>Операторы перебора  
  
|Оператор|Вычисление выражения|Инициализация|Приращение|  
|---------------|------------------|--------------------|---------------|  
|`while`|перед телом цикла|Нет|Нет|  
|`do`|после тела цикла|Нет|Нет|  
|`for`|перед телом цикла|Да|Да|  
|`for для диапазона`|перед телом цикла|Да|Да|  
  
 Часть с операторами оператора перебора не может быть объявлением. Однако она может быть составным оператором, содержащим объявление.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)
