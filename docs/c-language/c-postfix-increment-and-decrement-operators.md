---
title: Постфиксные операторы увеличения и уменьшения в C | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f96c48a69f692c8646de5dec8ad8e6431fb63c5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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