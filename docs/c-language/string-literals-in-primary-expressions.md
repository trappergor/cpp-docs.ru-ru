---
title: Строковые литералы в первичных выражениях
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
ms.openlocfilehash: 7d228f5ef4209ad47101240cb24429d6d502e9ca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521333"
---
# <a name="string-literals-in-primary-expressions"></a>Строковые литералы в первичных выражениях

"Строковый литерал" — это символ, расширенный символ или последовательность соседних символов, заключенных в двойные кавычки. Поскольку эти символы не являются переменными, ни строковые литералы, ни любой из их элементов не могут использоваться в качестве левого операнда в операции присваивания. Тип строкового литерала — это массив `char` (или массив `wchar_t` для двухбайтовых строковых литералов). Массивы в выражениях преобразуются в указатели. Дополнительные сведения о строках см. в статье [Строковые литералы](../c-language/c-string-literals.md).

## <a name="see-also"></a>См. также

[Первичные выражения в C](../c-language/c-primary-expressions.md)