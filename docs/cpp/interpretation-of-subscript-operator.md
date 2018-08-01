---
title: Интерпретация оператора индекса | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- subscript operator [C++], interpretation of
- arrays [C++], subscripting
- interpreting subscript operators [C++]
- operators [C++], interpretation of subscript
ms.assetid: 8852ca18-9d5b-43f7-b8bd-abc89364fbf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75659730198e09a172625c54bfcbdd54b7a9f857
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404792"
---
# <a name="interpretation-of-subscript-operator"></a>Интерпретация оператора индекса
Как и другие операторы, оператор индекса (**[]**) может быть переопределен пользователем. Поведение оператора индекса по умолчанию, если он не перегружен, — совмещать имя массива и индекс с помощью следующего метода.  
  
 \*((*имя массива*) + (*индекс*))  
  
 Как всегда в добавлениях, включающих типы указателей, масштабирование выполняется автоматически с учетом размера типа. Таким образом, результирующее значение не *индекс* байтов от начала координат *имя массива*; скорее, это *индекс*-й элемент массива. (Дополнительные сведения об этом преобразовании см. в разделе [Аддитивные операторы](../cpp/additive-operators-plus-and.md).)  
  
 Аналогично, для многомерных массивов адрес извлекается с использованием следующего метода.  
  
 **((**   
 ***имя массива* ) + ()**   
 ***Индекс* 1***max*2  *\* max*3 *.. .max*n) **+** *индекс*2  *\* max*3 *.. .max*n).   . . *+* *Индекс*n))  
  
## <a name="see-also"></a>См. также  
 [Массивы](../cpp/arrays-cpp.md)