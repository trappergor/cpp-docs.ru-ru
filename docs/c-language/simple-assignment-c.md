---
title: Простое назначение в C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31914118283c9d0c5c502e3426ba12e86d7c7680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="simple-assignment-c"></a>Простое назначение (C)
Оператор простого присваивания присваивает значение правого операнда левому операнду. Значения правого операнда преобразуется в тип выражения присваивания и заменяет значение, хранящееся в объекте, определяемом левым операндом. Применяются правила преобразования для назначений (см. статью [Преобразования назначений](../c-language/assignment-conversions.md)).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 В этом примере значение переменной `y` преобразуется в тип **double** и присваивается переменной `x`.  
  
## <a name="see-also"></a>См. также  
 [Операторы присваивания C](../c-language/c-assignment-operators.md)