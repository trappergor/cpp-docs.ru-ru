---
title: Интерпретация оператора индекса | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
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
ms.openlocfilehash: 6e1457744747ee3638d7f0b9485ac12af60e5cdd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058345"
---
# <a name="interpretation-of-subscript-operator"></a>Интерпретация оператора индекса

Как и другие операторы, оператор индекса (**\[]**) может быть переопределен пользователем. Поведение оператора индекса по умолчанию, если он не перегружен, — совмещать имя массива и индекс с помощью следующего метода.

\*((*имя массива*) + (*индекс*))

Как всегда в добавлениях, включающих типы указателей, масштабирование выполняется автоматически с учетом размера типа. Таким образом, результирующее значение не *индекс* байтов от начала координат *имя массива*; скорее, это *индекс*-й элемент массива. (Дополнительные сведения об этом преобразовании см. в разделе [Аддитивные операторы](../cpp/additive-operators-plus-and.md).)

Аналогично, для многомерных массивов адрес извлекается с использованием следующего метода.

((*имя массива*) + (*индекс*1 \* *max*2 \* *max*3 \* ... \* *max*n) + (*индекс*2 \* *max*3 \* ... \* *max*n) +... + *индекс*n))

## <a name="see-also"></a>См. также

[Массивы](../cpp/arrays-cpp.md)<br/>
