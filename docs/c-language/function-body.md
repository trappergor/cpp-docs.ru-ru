---
title: Текст функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6a566c1120f0a89a985895393fae5a79690bfa3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384682"
---
# <a name="function-body"></a>Текст функции
"Тело функции" — это составной оператор, содержащий операторы, которые определяют выполняемые функцией действия.  
  
## <a name="syntax"></a>Синтаксис  
 *function-definition*:  
 *declaration-specifiers* opt*attribute-seq* opt*declarator declaration-list* opt*compound-statement*  
  
 /\* *attribute-seq* Относится только к системам Microsoft */  
  
 *compound-statement*: /\* Текст функции \*/  
 **{**  *declaration-list* opt*statement-list* opt **}**  
  
 Если не указано иное, переменные, объявленные в теле функции (локальные переменные), имеют класс хранения **auto**. При вызове функции создается хранилище для локальных переменных и выполняются локальные инициализации. Управление передается первому оператору в составном выражении *compound-statement* и продолжается до тех пор, пока не будет выполнен оператор `return` или достигнут конец тела функции. Затем управление возвращается в точку, из которой вызвана функция.  
  
 Если функция должна возвращать значение, должен быть выполнен оператор `return`, содержащий выражение. Если оператор `return` не выполнен или если оператор `return` не содержит выражения, возвращаемое значение функции не определено.  
  
## <a name="see-also"></a>См. также  
 [Определения функций в C](../c-language/c-function-definitions.md)