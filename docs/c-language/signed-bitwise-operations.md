---
title: Битовые операции со знаком | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3ddd1c32beb5660fd1fa3c0160756734b4c1923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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