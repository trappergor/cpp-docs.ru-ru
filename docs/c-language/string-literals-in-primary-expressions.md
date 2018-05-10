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
ms.openlocfilehash: e5fd8c73bb9dac5a26c62b86bdc4038bd26a0829
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="string-literals-in-primary-expressions"></a>Строковые литералы в первичных выражениях
"Строковый литерал" — это символ, расширенный символ или последовательность соседних символов, заключенных в двойные кавычки. Поскольку эти символы не являются переменными, ни строковые литералы, ни любой из их элементов не могут использоваться в качестве левого операнда в операции присваивания. Тип строкового литерала — это массив `char` (или массив `wchar_t` для двухбайтовых строковых литералов). Массивы в выражениях преобразуются в указатели. Дополнительные сведения о строках см. в статье [Строковые литералы](../c-language/c-string-literals.md).  
  
## <a name="see-also"></a>См. также  
 [Первичные выражения в C](../c-language/c-primary-expressions.md)