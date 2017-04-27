---
title: "Постфиксные операторы | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: 7
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 2d456c0eb3add4fbcb7c968d3309625157922051
ms.lasthandoff: 04/01/2017

---
# <a name="postfix-operators"></a>Постфиксные операторы
Постфиксные операторы имеют самый высокий приоритет (наиболее тесную привязки) в вычислении выражений.  
  
## <a name="syntax"></a>Синтаксис  
 *postfix-expression*:  
 *primary-expression*  
  
 *postfix-expression*  **[**  *expression*  **]**  
  
 *postfix-expression*  **(**  *argument-expression-list* opt**)**  
  
 *postfix-expression*  **.**  *identifier*  
  
 *postfix-expression*  **->**  *identifier*  
  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 Операторы на этом уровне приоритета являются индексами массива, функциональными вызовами, структурными элементами и членами объединений, а также постфиксными операторами приращения и уменьшения.  
  
## <a name="see-also"></a>См. также  
 [Операторы в C](../c-language/c-operators.md)
