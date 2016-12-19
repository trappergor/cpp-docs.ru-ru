---
title: "Оператор преобразования в символы (#@) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#@"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#@ - оператор препроцессора"
  - "оператор преобразования в символы"
  - "препроцессор, операторы"
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Оператор преобразования в символы (#@)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Оператор образования символа может использоваться только в аргументах макросов.  Если перед формальным параметром в определении макроса стоят символы **\#@**, фактический аргумент заключается в одинарные кавычки и при разворачивании макроса обрабатывается как символ.  Например:  
  
```  
#define makechar(x)  #@x  
```  
  
 приводит к разворачиванию оператора  
  
```  
a = makechar(b);  
```  
  
 в выражение  
  
```  
a = 'b';  
```  
  
 В операторе образования символа не допускается использовать одинарные кавычки.  
  
 **Завершение блока, относящегося только к системам Microsoft**  
  
## См. также  
 [Операторы препроцессора](../preprocessor/preprocessor-operators.md)