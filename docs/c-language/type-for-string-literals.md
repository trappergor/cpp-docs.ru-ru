---
title: "Тип для строковых литералов | Microsoft Docs"
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
  - "строковые литералы, тип"
  - "типы [C], строковые литералы"
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Тип для строковых литералов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Строковые литералы имеют тип массива `char` \(т. е., **char\[ \]**\). \(Строки расширенных символов имеют тип массива `wchar_t` \(т. е., **wchar\_t \[\]**\).\) Это означает, что строка является массивом с элементами типа `char`.  Число элементов в массиве равно числу символов в строке плюс один дополнительный элемент для завершающего символа null.  
  
## См. также  
 [Строковые литералы в C](../c-language/c-string-literals.md)