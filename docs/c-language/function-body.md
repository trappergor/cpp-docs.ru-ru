---
title: "Текст функции | Документация Майкрософт"
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
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: a73f66ed65754897017af40988522e344c725a7c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
