---
title: "Битовые операции со знаком | Документы Майкрософт"
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
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 9ffc5335bb28e619f166a524083937d17a59bb97
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="signed-bitwise-operations"></a>Битовые операции со знаком
**ANSI 3.3** Результаты выполнения побитовых операций над знаковыми целочисленными значениями  
  
 Побитовые операции над знаковыми целочисленными значениями работают так же, как и над беззнаковыми. Например, значение `-16 & 99` можно представить в двоичном виде следующим образом:  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 Результат выполнения побитовой операции И будет равен 96.  
  
## <a name="see-also"></a>См. также  
 [Целые числа](../c-language/integers.md)
