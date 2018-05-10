---
title: Обзор операторов C | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3cf80e6237b21101f737f496eb39688ec6ed0a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="overview-of-c-statements"></a>Общие сведения об операторах в C
Операторы языка C состоят из токенов, выражений и других операторов. Оператор, который формирует компонент или другой оператор, называется телом внешнего оператора. В этом разделе рассматриваются все типы операторов, которые задаются следующим синтаксисом:  
  
## <a name="syntax"></a>Синтаксис  
 *statement*:  
 [labeled-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound-statement](../c-language/compound-statement-c.md)  
  
 [expression-statement](../c-language/expression-statement-c.md)  
  
 [selection-statement](../c-language/if-statement-c.md)  
  
 [iteration-statement](../c-language/do-while-statement-c.md)  
  
 [jump-statement](../c-language/break-statement-c.md)  
  
 [try-except-statement](../c-language/try-except-statement-c.md)  
  
 /* Относится только к системам Microsoft \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Относится только к системам Microsoft \*/  
  
 Тело оператора часто представляет собой составной оператор, то есть состоит из других операторов, которые могут содержать ключевые слова. Составные операторы разграничиваются фигурными скобками (**{ }**). Все остальные операторы C заканчиваются точкой с запятой (**;**). Точка с запятой является признаком конца оператора.  
  
 Оператор выражения содержит выражение на языке C, которое может содержать арифметические или логические операторы, представленные в статье [Выражения и присваивания](../c-language/expressions-and-assignments.md). Неопределенный оператор представляет собой пустой оператор.  
  
 Любой оператор C может начинаться с метки-идентификатора, которая состоит из имени и двоеточия. Поскольку метки операторов распознает только оператор `goto`, они рассматриваются в разделе, посвященном оператору `goto`. Дополнительные сведения см. в статье [goto и помеченные операторы (C)](../c-language/goto-and-labeled-statements-c.md).  
  
## <a name="see-also"></a>См. также  
 [Операторы](../c-language/statements-c.md)