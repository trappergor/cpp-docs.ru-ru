---
title: "Преобразования вызова функции | Документация Майкрософт"
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
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 35eee1be7c509d1d4bb6267164ec90e48c94d1d1
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="function-call-conversions"></a>Преобразования вызова функции
Тип преобразования, выполняемого над аргументами в вызове функции, зависит от того, имеется ли для вызываемой функции прототип функции (предварительное объявление) с объявленными типами аргументов.  
  
 Если существует прототип функции и в нем объявлены типы аргументов, то компилятор выполняет проверку типа (см. статью [Функции](../c-language/functions-c.md)).  
  
 Если прототипа нет, то над аргументами в вызове функции выполняются только обычные арифметические преобразования. Для каждого аргумента в вызове они выполняются отдельно. Иными словами, значение **float** преобразуется в **double**, значение `char` или **short** — в `int`, а значение `unsigned char` или **unsigned short** преобразуется в `unsigned int`.  
  
## <a name="see-also"></a>См. также  
 [Преобразования типов](../c-language/type-conversions-c.md)
