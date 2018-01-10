---
title: "Текст функции | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a0c85ecf0752ff34bf5b61e42309360f2bc4d448
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="function-body"></a>Текст функции
"Тело функции" — это составной оператор, содержащий операторы, которые определяют выполняемые функцией действия.  
  
## <a name="syntax"></a>Синтаксис  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* Относится только к системам Microsoft */  
  
 *compound-statement*: /\* Текст функции \*/  
 **{**  *declaration-list* opt*statement-list* opt**}**  
  
 Если не указано иное, переменные, объявленные в теле функции (локальные переменные), имеют класс хранения **auto**. При вызове функции создается хранилище для локальных переменных и выполняются локальные инициализации. Управление передается первому оператору в составном выражении *compound-statement* и продолжается до тех пор, пока не будет выполнен оператор `return` или достигнут конец тела функции. Затем управление возвращается в точку, из которой вызвана функция.  
  
 Если функция должна возвращать значение, должен быть выполнен оператор `return`, содержащий выражение. Если оператор `return` не выполнен или если оператор `return` не содержит выражения, возвращаемое значение функции не определено.  
  
## <a name="see-also"></a>См. также  
 [Определения функций в C](../c-language/c-function-definitions.md)