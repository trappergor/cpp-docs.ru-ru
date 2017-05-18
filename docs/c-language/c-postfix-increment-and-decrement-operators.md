---
title: "Постфиксные операторы увеличения и уменьшения в C | Документы Майкрософт"
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
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: a67e01fe0555a628c8b2178cc580bcaa8f84cd83
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="c-postfix-increment-and-decrement-operators"></a>Постфиксные операторы увеличения и уменьшения в C
Операнды операторов постфиксных инкремента и декремента являются скалярными типами, представляющими собой изменяемые L-значения.  
  
## <a name="syntax"></a>Синтаксис  
 *postfix-expression*:  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 Результатом операции постфиксного инкремента или декремента является значение операнда. После получения результата значение операнда инкрементируется (или декрементируется). В следующем примере кода демонстрируется оператор постфиксного инкремента.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 В этом примере переменная `var` сравнивается с нулем и затем инкрементируется. Если значение `var` до инкрементирования было положительным, выполняется следующий оператор. Сначала значение объекта, на который указывает `q`, присваивается объекту, на который указывает `p`. Затем `q` и `p` инкрементируются.  
  
## <a name="see-also"></a>См. также  
 [Постфиксные операторы увеличения и уменьшения: ++ и --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)
