---
title: "Простое назначение в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- type conversion [C++], simple assignment
- data type conversion [C++], simple assignment
- operators [C], simple assignment
- assignment operators [C++], simple
- simple assignment operator
- equal sign
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1cf9c5675affb6dcaea78e0cabf2a4427ad03938
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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