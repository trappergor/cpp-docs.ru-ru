---
title: "___lc_locale_name_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___lc_locale_name_func"
apilocation: 
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___lc_locale_name_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___lc_locale_name_func"
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# ___lc_locale_name_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренняя функция CRT.  Получает имя текущего языкового стандарта потока.  
  
## Синтаксис  
  
```cpp  
wchar_t** ___lc_locale_name_func(void);  
```  
  
## Возвращаемое значение  
 Указатель на строку, которая содержит имя текущего языкового стандарта потока.  
  
## Заметки  
 `___lc_locale_name_func` — это внутренняя функция CRT, которая используется другими функциями CRT для получения текущего языкового стандарта из локального хранилища потока для данных CRT.  Эти сведения также доступны при использовании функции [\_get\_current\_locale](../Topic/_get_current_locale.md) или [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  
  
 Внутренние функции CRT связаны с конкретной реализацией и подлежат изменению в каждом выпуске.  Мы не рекомендуем использовать их в коде.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`___lc_locale_name_func`|crt\\src\\setlocal.h|  
  
## См. также  
 [\_get\_current\_locale](../Topic/_get_current_locale.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_create\_locale, \_wcreate\_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [\_free\_locale](../c-runtime-library/reference/free-locale.md)