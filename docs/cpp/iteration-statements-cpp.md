---
title: Операторы перебора (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- iteration statements
- loop structures, iteration statements
ms.assetid: bf6d75f7-ead2-426a-9c47-33847f59b8c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 988d46b3f4b2e20ff14227fda70a6f39ac95756c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402901"
---
# <a name="iteration-statements-c"></a>Операторы перебора (C++)
Операторы итерации приводят к тому, что операторы (или составные операторы) выполняются ноль или более раз в соответствии с некоторыми критериями завершения цикла. Когда эти операторы являются составными операторами, они выполняются по порядку, если в них не встречается инструкция [break](../cpp/break-statement-cpp.md) или [continue](../cpp/continue-statement-cpp.md).  
  
 В C++ есть четыре оператора итерации:[while](../cpp/while-statement-cpp.md), [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md), и [for для диапазона](../cpp/range-based-for-statement-cpp.md). Каждый из них выполняет повтор, пока его выражение завершения не примет значение ноль или цикл не будет принудительно завершен инструкцией **break**. В следующей таблице приведены сводные сведения об этих операторах и их действии. Дополнительные сведения о каждом из них см. в последующих разделах.  
  
### <a name="iteration-statements"></a>Операторы итерации  
  
|Оператор|Вычисление выражения|Инициализация|Приращение|  
|---------------|------------------|--------------------|---------------|  
|**while**|перед телом цикла|Нет|Нет|  
|**do**|после тела цикла|Нет|Нет|  
|**for**|перед телом цикла|Да|Да|  
|**for для диапазона**|перед телом цикла|Да|Да|  
  
 Выражение в операторе перебора не может быть объявлением. Однако оно может быть составным оператором, содержащим объявление.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)