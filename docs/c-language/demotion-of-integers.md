---
title: Понижение уровня целых чисел | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d380fd36cc71b6d188bbbfe8e51ce3185405611
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381724"
---
# <a name="demotion-of-integers"></a>Понижение уровня целых чисел
**ANSI 3.2.1.2** Результат преобразования целого числа в более короткое целое число со знаком или результат преобразования целого числа без знака в целое число со знаком той же длины, если представление значения невозможно.  
  
 Когда целое число типа **long** приводится к типу **short** или тип **short** приводится к типу `char`, младшие байты сохраняются.  
  
 Например, строкой  
  
```  
short x = (short)0x12345678L;  
```  
  
 переменной `x` присваивается значение 0x5678, а строкой  
  
```  
char y = (char)0x1234;  
```  
  
 переменной `y` присваивается значение 0x34.  
  
 При преобразовании переменных со знаком в переменные без знака и наоборот битовые шаблоны не изменяются. Например, при приведении значения -2 (0xFE) к значению без знака получается значение 254 (также 0xFE).  
  
## <a name="see-also"></a>См. также  
 [Целые числа](../c-language/integers.md)