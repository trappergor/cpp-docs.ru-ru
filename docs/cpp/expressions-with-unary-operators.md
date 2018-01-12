---
title: "Выражения с унарными операторами | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- expressions [C++], unary operators
- unary operators [C++], expressions with
- expressions [C++], operators
ms.assetid: 1217685b-b85d-4b48-9ff4-d90f56a26c1b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44485f0c5749db36ececd2061955f9956cb49ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-with-unary-operators"></a>Выражения с унарными операторами
Унарные операторы действуют только на один операнд в выражении. Ниже приводится список унарных операторов:  
  
-   [Оператор косвенного обращения (*)](../cpp/indirection-operator-star.md)  
  
-   [Оператор взятия адреса (&)](../cpp/address-of-operator-amp.md)  
  
-   [Оператор (+) унарного сложения](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [Оператор унарного отрицания (-)](../cpp/unary-plus-and-negation-operators-plus-and.md)  
  
-   [Оператор логического отрицания (!)](../cpp/logical-negation-operator-exclpt.md)  
  
-   [Оператор дополнения (~)](../cpp/one-s-complement-operator-tilde.md)  
  
-   [Префиксный оператор инкремента (++)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Оператор префиксного декремента (--)](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md)  
  
-   [Оператор приведения)](../cpp/cast-operator-parens.md)  
  
-   [оператор sizeof](../cpp/sizeof-operator.md)  
  
-   [оператор __uuidof](../cpp/uuidof-operator.md)  
  
-   [оператор __alignof](../cpp/alignof-operator.md)  
  
-   [оператор New](../cpp/new-operator-cpp.md)  
  
-   [оператор delete](../cpp/delete-operator-cpp.md)  
  
 Эти операторы имеют ассоциативность справа налево. Обычно синтаксис унарных выражений предшествует синтаксису постфиксных или основных выражений.  
  
 Ниже перечислены возможные формы унарных выражений.  
  
-   *postfix-expression*  
  
-   `++`*унарное выражение*  
  
-   `--`*унарное выражение*  
  
-   *унарный оператор* *выражение приведения*  
  
-   `sizeof`*унарное выражение*  
  
-   `sizeof(`*имя типа*`)`  
  
-   `decltype(`*выражение*`)`  
  
-   *выражение выделения*  
  
-   *освобождение выражения*  
  
 Любой *Постфиксное выражение* считается *унарное выражение*, а потому, что любой основное выражение считается *Постфиксное выражение*, — все первичные выражения считается *унарное выражение* также. Дополнительные сведения см. в разделе [постфиксные выражения](../cpp/postfix-expressions.md) и [первичные выражения](../cpp/primary-expressions.md).  
  
 Объект *унарный оператор* состоит из одной или нескольких из следующих символов:`* & + - ! ~`  
  
 *Выражение приведения* является унарное выражение с необязательным приведения, чтобы изменить тип. Дополнительные сведения см. [оператор Cast: ()](../cpp/cast-operator-parens.md).  
  
 *Выражение* может быть любым выражением. Дополнительные сведения см. в разделе [выражений](../cpp/expressions-cpp.md).  
  
 *Выражение выделения* ссылается на `new` оператор. *Освобождения выражение* ссылается на `delete` оператор. Дополнительные сведения см. по ссылкам, приведенным выше.  
  
## <a name="see-also"></a>См. также  
 [Типы выражений](../cpp/types-of-expressions.md)