---
title: "Интерпретация оператора индекса | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1a83ff6aea4380688d3b6298b93e04caab1dbb7f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="interpretation-of-subscript-operator"></a>Интерпретация оператора индекса
Как и другие операторы, оператор индекса (**[]**) может быть переопределен пользователем. Поведение оператора индекса по умолчанию, если он не перегружен, — совмещать имя массива и индекс с помощью следующего метода.  
  
 \*((*имя массива*) + (*индекс*))  
  
 Как всегда в добавлениях, включающих типы указателей, масштабирование выполняется автоматически с учетом размера типа. Таким образом, конечное значение не *индекс* байтов от начала координат *имя массива*; вместо этого он *индекс*й элемент массива. (Дополнительные сведения об этом преобразовании см. в разделе [Аддитивные операторы](../cpp/additive-operators-plus-and.md).)  
  
 Аналогично, для многомерных массивов адрес извлекается с использованием следующего метода.  
  
 **((**   
 ***имя массива* ) + ()**   
 ***Индекс* 1***max*2 * \* max*3*...max*n) ** + ** *индекс*2 * \* max*3*...max*n).   . . *+**индекс*n))  
  
## <a name="see-also"></a>См. также  
 [Массивы](../cpp/arrays-cpp.md)
