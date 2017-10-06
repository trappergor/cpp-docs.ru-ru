---
title: "Идентификаторы в первичных выражениях | Документация Майкрософт"
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
- identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 90fa27300457a2318b57fd16ab78688c771651c7
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="identifiers-in-primary-expressions"></a>Идентификаторы в первичных выражениях
Идентификаторы могут иметь целочисленный тип, тип **float**, тип `enum`, тип `struct`, тип **объединения**, тип массива, тип указателя или тип функции. Идентификатор представляет собой основное выражение, его он был объявлен как обозначение объекта (тогда это l-значение) или как функция (тогда это обозначение функции). Определение левостороннего значения приводится в статье [Выражения L-Value и R-Value](../c-language/l-value-and-r-value-expressions.md).  
  
 Значение указателя, представленное идентификатором массива, не является переменной, поэтому идентификатор массива не может быть левым операндом операции присваивания и, следовательно, не является изменяемым l-значением.  
  
 Идентификатор, объявленный как функция, представляет собой указатель, значением которого является адрес функции. Указатель адресует функцию, возвращающую значение указанного типа. Таким образом, идентификаторы функций также не могут быть l-значениями в операциях присваивания. Дополнительные сведения см. в статье [Идентификаторы](../c-language/c-identifiers.md).  
  
## <a name="see-also"></a>См. также  
 [Первичные выражения в C](../c-language/c-primary-expressions.md)
