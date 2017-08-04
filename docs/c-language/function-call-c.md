---
title: "Вызов функций в C | Документация Майкрософт"
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
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a86b3e45b5a5ce8c681fe267b7de8386b5fbc5c2
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="function-call-c"></a>Вызов функций (C)
Вызов функции — это выражение, содержащее имя вызываемой функции или значение указателя функции и, при необходимости, аргументы, передаваемые в эту функцию.  
  
## <a name="syntax"></a>Синтаксис  
 *postfix-expression*:  
 *postfix-expression*  **(**  *argument-expression-list* opt**)**  
  
 *argument-expression-list*:  
 *assignment-expression*  
  
 *argument-expression-list*  **,**  *assignment-expression*  
  
 Выражение *postfix-expression* должно вычислять адрес функции (например, идентификатор функции или значение указателя функции), а *argument-expression-list* содержит список выражений (разделенных запятыми), значения которых (аргументы) передаются функции. Аргумент *argument-expression-list* может быть пустым.  
  
 Выражение вызова функции имеет значение и тип возвращаемого значения функции. Функция не может возвращать объект типа массива. Если тип возвращаемого значения функции — `void` (то есть объявлено, что функция никогда не возвращает значение), выражение вызова функции также имеет тип `void`. (Дополнительные сведения см. в разделе [Вызовы функций](../c-language/function-calls.md).)  
  
## <a name="see-also"></a>См. также  
 [Оператор вызова функции: ()](../cpp/function-call-operator-parens.md)
