---
title: "Строковые литералы в первичных выражениях | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d1ed5731f0b46769ac9f49c34752d8794a0dddc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="string-literals-in-primary-expressions"></a>Строковые литералы в первичных выражениях
"Строковый литерал" — это символ, расширенный символ или последовательность соседних символов, заключенных в двойные кавычки. Поскольку эти символы не являются переменными, ни строковые литералы, ни любой из их элементов не могут использоваться в качестве левого операнда в операции присваивания. Тип строкового литерала — это массив `char` (или массив `wchar_t` для двухбайтовых строковых литералов). Массивы в выражениях преобразуются в указатели. Дополнительные сведения о строках см. в статье [Строковые литералы](../c-language/c-string-literals.md).  
  
## <a name="see-also"></a>См. также  
 [Первичные выражения в C](../c-language/c-primary-expressions.md)