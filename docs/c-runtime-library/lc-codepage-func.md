---
title: "___lc_codepage_func | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___lc_codepage_func"
apilocation: 
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "lc_codepage_func"
  - "___lc_codepage_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_codepage_func"
ms.assetid: 6a663bd0-5a63-4a2f-9507-872ec1582aae
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ___lc_codepage_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренняя функция CRT.  Получает текущую кодовую страницу потока.  
  
## Синтаксис  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## Возвращаемое значение  
 Текущая кодовая страница потока.  
  
## Заметки  
 `___lc_codepage_func` — это внутренняя функция CRT, которая используется другими функциями CRT для получения текущей кодовой страницы из локального хранилища потока для данных CRT.  Эти сведения также доступны при использовании функции [\_get\_current\_locale](../Topic/_get_current_locale.md).  
  
 *Кодовая страница* представляет собой сопоставление однобайтовых или двухбайтовых кодов с конкретными символами.  Разные кодовые страницы включают разные специальные символы, как правило, настроенные для языка или группы языков.  Дополнительные сведения о кодовых страницах см. в разделе [Кодовые страницы](../c-runtime-library/code-pages.md).  
  
 Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске.  Мы не рекомендуем использовать их в коде.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`___lc_codepage_func`|crt\\src\\setlocal.h|  
  
## См. также  
 [\_get\_current\_locale](../Topic/_get_current_locale.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)