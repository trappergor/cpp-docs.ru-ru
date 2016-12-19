---
title: "Сопоставления констант и глобальных переменных | Microsoft Docs"
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
  - "_tenviron"
  - "_TEOF"
  - "_tfinddata_t"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tenviron - функция"
  - "_TEOF - тип"
  - "_tfinddata_t - функция"
  - "универсальные текстовые сопоставления"
  - "tenviron - функция"
  - "TEOF - тип"
  - "tfinddatat - функция"
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Сопоставления констант и глобальных переменных
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти универсальные текстовые константы, глобальные переменные и сопоставления стандартного типа определяются в TCHAR.H и зависят от того, была ли в вашей программе определена константа `_UNICODE` или `_MBCS`.  
  
### Сопоставления универсальных текстовых констант и глобальных переменных  
  
|Универсальный текст — имя объекта|SBCS \(\_UNICODE, \_MBCS не определены\)|\_MBCS определено|\_UNICODE определено|  
|---------------------------------------|----------------------------------------------|-----------------------|--------------------------|  
|`_TEOF`|`EOF`|`EOF`|`WEOF`|  
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## См. также  
 [Универсальные текстовые сопоставления](../c-runtime-library/generic-text-mappings.md)   
 [Сопоставления типов данных](../c-runtime-library/data-type-mappings.md)   
 [Сопоставления процедур](../c-runtime-library/routine-mappings.md)   
 [Пример программы, использующей обычный текст](../c-runtime-library/a-sample-generic-text-program.md)   
 [Использование универсальных текстовых сопоставлений](../c-runtime-library/using-generic-text-mappings.md)