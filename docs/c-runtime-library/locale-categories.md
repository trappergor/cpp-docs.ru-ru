---
title: "Категории языковых стандартов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LC_MAX"
  - "LC_MIN"
  - "LC_MONETARY"
  - "LC_TIME"
  - "LC_NUMERIC"
  - "LC_COLLATE"
  - "LC_CTYPE"
  - "LC_ALL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LC_ALL - константа"
  - "LC_COLLATE - константа"
  - "LC_CTYPE - константа"
  - "LC_MAX - константа"
  - "LC_MIN - константа"
  - "LC_MONETARY - константа"
  - "LC_NUMERIC - константа"
  - "LC_TIME - константа"
  - "константы языковых стандартов"
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Категории языковых стандартов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <locale.h>  
  
```  
  
## Заметки  
 Категории языкового являются константами манифеста, используемыми процедурами локализации для определения, какая часть данных о языковом стандарте программы будет использоваться.  Языковой стандарт ссылается на расположение \(или страну\/регион\), для которого некоторые аспекты программы можно настраивать.  Категориям, зависящие от языкового стандарта, включают в себя, например, формат дат и отображения денежных значений.  
  
|Категория языкового стандарта|Затрагиваемые части программы|  
|-----------------------------------|-----------------------------------|  
|`LC_ALL`|Все поведения, зависящие от языкового стандарта \(все категории\)|  
|`LC_COLLATE`|Поведение функций `strcoll` и `strxfrm`|  
|`LC_CTYPE`|Поведение функций, обрабатывающих символы \(за исключением **isdigit**, `isxdigit`, `mbstowcs` и `mbtowc`, которые не изменяются\)|  
|`LC_MAX`|Эквивалентно `LC_TIME`|  
|`LC_MIN`|Эквивалентно `LC_ALL`|  
|`LC_MONETARY`|Информация от форматировании валют возвращается функцией `localeconv`|  
|`LC_NUMERIC`|Информация о символе десятичной запятой для форматированного вывода процедур \(например, `printf`\), процедурах преобразования данных, и невалютном форматировании возвращается функцией `localeconv`|  
|`LC_TIME`|Поведение функции `strftime`|  
  
 Пример см. в разделе [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md).  
  
## См. также  
 [localeconv](../c-runtime-library/reference/localeconv.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [Функции strcoll](../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, \_strxfrm\_l, \_wcsxfrm\_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)