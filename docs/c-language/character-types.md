---
title: "Символьные типы | Microsoft Docs"
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
  - "типы данных символов [C]"
  - "типы [C], знак"
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Символьные типы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Целая символьная константа, в начале которой не указана буква **L**, имеет тип `int`.  Значением целой символьной константы, содержащей один символ, является численное значение символа, интерпретированное как целое число.  Например, численное значение символа `a` равно 97 в десятичном представлении и 61 в шестнадцатеричном представлении.  
  
 Синтаксически "расширенная символьная константа" представляет собой символьную константу с префиксом в виде буквы **L**.  Расширенная символьная константа имеет тип `wchar_t` — целочисленный тип, определенный в файле заголовка STDDEF.H.  Например:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Расширенные символьные константы имеют ширину 16 бит и указывают члены расширенной кодировки выполнения.  Они обеспечивают представление символов в алфавитах, слишком больших для представления типом `char`.  Дополнительные сведения о расширенных символах см. в разделе [Многобайтовые и расширенные символы](../Topic/Multibyte%20and%20Wide%20Characters.md).  
  
## См. также  
 [Константы символов в C](../Topic/C%20Character%20Constants.md)