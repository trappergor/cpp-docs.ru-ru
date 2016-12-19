---
title: "_free_locale | Microsoft Docs"
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
  - "_free_locale"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-locale-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__free_locale"
  - "free_locale"
  - "_free_locale"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__free_locale - функция"
  - "_free_locale - функция"
  - "free_locale - функция"
  - "язык и региональные стандарты, освобождение"
ms.assetid: 1f08d348-ab32-4028-a145-6cbd51b49af9
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _free_locale
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Освобождает объект языкового стандарта.  
  
## Синтаксис  
  
```  
void _free_locale(  
   _locale_t locale  
);  
```  
  
#### Параметры  
 `locale`  
 Объект языкового стандарта, который необходимо освободить.  
  
## Заметки  
 Функция `_free_locale` используется, чтобы освободить объект языкового стандарта, полученный из вызова `_get_current_locale` или `_create_locale`.  
  
 Предыдущее название данной функции `__free_locale` \(с 2 символами подчеркивания в начале\) использовать не рекомендуется.  
  
## Требования  
  
|`Routine`|Обязательный заголовок|  
|---------------|----------------------------|  
|`_free_locale`|\<locale.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Эквивалент в .NET Framework  
 Эквивалента нет.  
  
## См. также  
 [\_get\_current\_locale](../Topic/_get_current_locale.md)   
 [\_create\_locale, \_wcreate\_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)