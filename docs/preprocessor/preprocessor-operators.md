---
title: "Операторы препроцессора | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "операторы [C++], препроцессор"
  - "операторы препроцессора"
ms.assetid: 884126d1-0ce2-48b6-9e06-8a2d7c4a9656
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Операторы препроцессора
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В контексте директивы `#define` используются четыре оператора, относящихся к препроцессору \(краткую информацию о них см. в приведенной ниже таблице\).  В следующих трех разделах рассматриваются преобразования в строку, преобразования в символы и вставки токенов.  Дополнительные сведения см. в разделе об операторе **defined** см. в разделе [Директивы \#if, \#elif, \#else и \#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
|Оператор|Действие|  
|--------------|--------------|  
|[Оператор преобразования в строку \(\#\)](../preprocessor/stringizing-operator-hash.md)|В результате его выполнения соответствующий аргумент заключается в двойные кавычки|  
|[Оператор преобразования в символы \(\#@\)](../preprocessor/charizing-operator-hash-at.md)|В результате его выполнения соответствующий аргумент заключается в одиночные кавычки и рассматривается как символ \(относится только к системам Microsoft\)|  
|[Оператор вставки токенов \(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md)|Выполняет конкатенацию токенов, используемых в качестве фактических аргументов, для создания других токенов|  
|[оператор defined](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|Упрощает написание составных выражений в некоторых директивах макросов|  
  
## См. также  
 [Директивы препроцессора](../preprocessor/preprocessor-directives.md)   
 [Предустановленный макрос](../preprocessor/predefined-macros.md)   
 [Справочник по препроцессору C\/C\+\+](../preprocessor/c-cpp-preprocessor-reference.md)