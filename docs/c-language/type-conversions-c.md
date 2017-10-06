---
title: "Преобразования типов | Документация Майкрософт"
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
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b2d02ad9494bce2c1d9a0e94cd87c9327526e2f3
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="type-conversions-c"></a>Преобразования типов (C)
Преобразования типов зависят от указанного оператора и типа операнда или операторов. Преобразования типов выполняются в следующих случаях:  
  
-   Когда значение одного типа присваивается переменной другого типа или оператор преобразует тип своего операнда или операндов до выполнения операции  
  
-   Когда значение одного типа явно приводится к другому типу  
  
-   Когда значение передается в качестве аргумента в функцию или когда тип возвращается из функции  
  
 Символ, короткое целое число или целое битовое поле, со знаком или без, а также объект типа перечисления можно использовать в выражении везде, где можно использовать целое число. Если `int` может представлять все значения исходного типа, значение преобразуется в `int`; в противном случае оно преобразуется в `unsigned int`. Этот процесс называется "восходящим приведением целого типа". Восходящее приведение целого типа сохраняет значение. То есть гарантируется, что значение после приведения будет таким же, как до него. Дополнительные сведения есть в статье [Обычные арифметические преобразования](../c-language/usual-arithmetic-conversions.md).  
  
## <a name="see-also"></a>См. также  
 [Выражения и присваивания](../c-language/expressions-and-assignments.md)
