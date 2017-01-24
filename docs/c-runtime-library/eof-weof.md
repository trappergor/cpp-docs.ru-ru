---
title: "EOF, WEOF | Microsoft Docs"
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
  - "EOF"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "EOF - функция"
  - "WEOF - функция"
  - "конец файла"
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EOF, WEOF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <stdio.h>  
```  
  
## Заметки  
 EOF возвращается процедурой ввода\-вывода, когда достигнут конец файла \(или в некоторых случаях ошибка\).  
  
 WEOF формирует возвращаемое значение типа **wint\_t**, которое используется для обозначения конца расширенного потока или для сообщения об ошибке.  
  
## См. также  
 [putc, putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../Topic/fflush.md)   
 [fclose, \_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [\_putch, \_putwch](../Topic/_putch,%20_putwch.md)   
 [isascii, \_\_isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)