---
title: Строковые литералы в первичных выражениях | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 818284a0eabce779d9f52e8fe7b3af4cc1d8df4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095533"
---
# <a name="string-literals-in-primary-expressions"></a>Строковые литералы в первичных выражениях

"Строковый литерал" — это символ, расширенный символ или последовательность соседних символов, заключенных в двойные кавычки. Поскольку эти символы не являются переменными, ни строковые литералы, ни любой из их элементов не могут использоваться в качестве левого операнда в операции присваивания. Тип строкового литерала — это массив `char` (или массив `wchar_t` для двухбайтовых строковых литералов). Массивы в выражениях преобразуются в указатели. Дополнительные сведения о строках см. в статье [Строковые литералы](../c-language/c-string-literals.md).

## <a name="see-also"></a>См. также

[Первичные выражения в C](../c-language/c-primary-expressions.md)