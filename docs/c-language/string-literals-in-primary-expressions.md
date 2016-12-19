---
title: "Строковые литералы в первичных выражениях | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "строковые литералы, в первичных выражениях"
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Строковые литералы в первичных выражениях
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"Строковый литерал" — это символ, расширенный символ или последовательность соседних символов, заключенных в двойные кавычки.  Поскольку эти символы не являются переменными, ни строковые литералы, ни любой из их элементов не могут использоваться в качестве левого операнда в операции присваивания.  Тип строкового литерала — это массив `char` \(или массив `wchar_t` для двухбайтовых строковых литералов\).  Массивы в выражениях преобразуются в указатели.  Дополнительные сведения о строках см. в разделе [Строковые литералы](../c-language/c-string-literals.md).  
  
## См. также  
 [Первичные выражения в C](../c-language/c-primary-expressions.md)