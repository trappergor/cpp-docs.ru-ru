---
title: "Составное назначение C | Документы Майкрософт"
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
- operators [C], assignment
- compound assignment operators
- assignment operators, compound
ms.assetid: db7b5893-cd56-4f1c-9981-5a024200ab63
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 85fb149dcfb104a9b2e094deef83c3b33d1b7b6c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="c-compound-assignment"></a>Составное назначение C
Составные операторы присваивания объединяют оператор простого присваивания с другим бинарным оператором. Составные операторы присваивания выполняют операцию, заданную дополнительными оператором, затем присваивают результат левому операнду. Например, составное выражение присваивания  
  
```  
  
expression1  
+=  
expression2  
  
```  
  
 можно понимать как  
  
```  
  
expression1  
=  
expression1  
+  
expression2  
  
```  
  
 Но составной оператор присваивания не эквивалентен своей развернутой версии, так как в составном операторе присваивания выражение *выражение1* вычисляется только один раз, а в развернутой версии выражение *выражение1* вычисляется дважды: в операции сложения и в операции присваивания.  
  
 Операнды составного оператора присваивания должны быть целочисленного типа или типа с плавающей запятой. Каждый составной оператор присваивания выполняет те же преобразования, что и соответствующий бинарный оператор, и соответственно ограничивает типы своих операндов. Левый операнд операторов сложения с присваиванием (`+=`) и вычитания с присваиванием (**-=**) может иметь тип указателя, при этом правый операнд должен быть целочисленного типа. Результат составной операции присваивания имеет значение и тип левого операнда.  
  
```  
#define MASK 0xff00  
  
n &= MASK;  
```  
  
 В этом примере операция побитового включающего AND выполняется для `n` и `MASK`, а результат присваивается переменной `n`. Константа манифеста `MASK` определяется с помощью директивы препроцессора [#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## <a name="see-also"></a>См. также  
 [Операторы присваивания C](../c-language/c-assignment-operators.md)
