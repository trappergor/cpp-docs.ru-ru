---
title: "_setmbcp | Microsoft Docs"
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
  - "_setmbcp"
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
  - "_setmbcp"
  - "setmbcp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmbcp - функция"
  - "многобайтовые кодовые страницы"
  - "setmbcp - функция"
ms.assetid: cfde53b5-0b73-4684-81b1-a8d3aafc85de
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmbcp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает новую многобайтовую кодовую страницу.  
  
## Синтаксис  
  
```  
int _setmbcp(  
   int codepage   
);  
```  
  
#### Параметры  
 `codepage`  
 Новый параметр кодовой страницы для независимых от языкового стандарта многобайтовых процедур.  
  
## Возвращаемое значение  
 Возвращает 0, если кодовая страница задана успешно.  Если недопустимое значение кодовой страницы передается в качестве `codepage`, возвращает \-1 и не изменяет параметр кодовой страницы.  Устанавливает `errno` в `EINVAL`, если происходит сбой выделения памяти.  
  
## Заметки  
 Функция `_setmbcp` определяет новую многобайтовую кодовую страницу.  По умолчанию система времени выполнения автоматически задает многобайтовую кодовую страницу в системную кодовую страницу по умолчанию ANSI.  Параметр многобайтовой кодовой страницы влияет на все не зависящие от языкового стандарта процедуры.  Однако можно указать `_setmbcp` использовать кодовую страницу, определенную для текущего языкового стандарта \(см. следующий список констант манифеста и соответствующих результатов поведения\).  Список процедур, которые зависят от кодовой страницей языкового стандарта, а не от многобайтовой кодовой страницы см. в разделе [Interpretation of Multibyte\-Character Sequences](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md).  
  
 Многобайтовая кодовая страница также влияет на обработку многобайтовых символов следующими процедурами библиотеки времени выполнения:  
  
||||  
|-|-|-|  
|[функции \_exec](../../c-runtime-library/exec-wexec-functions.md)|[\_mktemp](../../c-runtime-library/reference/mktemp-wmktemp.md)|[\_stat](../../c-runtime-library/reference/stat-functions.md)|  
|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[функции \_spawn](../Topic/_spawn,%20_wspawn%20Functions.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md)|[\_splitpath](../Topic/_splitpath,%20_wsplitpath.md)|[tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
  
 Кроме того, все процедуры библиотеки времени выполнения, которые получают многобайтовые аргументы программы `argv` или `envp` \(например, семейства `_exec` и `_spawn`\), обрабатывают эти строки в соответствии с многобайтовой кодовой страницей.  Следовательно, на эти процедуры также влияет вызов `_setmbcp`, изменяющий многобайтовую кодовую страницу.  
  
 Для аргумента `codepage` может быть установлено одно из следующих значений:  
  
-   `_MB_CP_ANSI` Используется кодовая страница ANSI, полученная от операционной системы при запуске программы.  
  
-   `_MB_CP_LOCALE` Используется кодовая страница текущего языкового стандарта, полученная из предыдущего вызова [setlocale](../Topic/setlocale,%20_wsetlocale.md).  
  
-   `_MB_CP_OEM` Используется кодовая страница OEM, полученная от операционной системы при запуске программы.  
  
-   `_MB_CP_SBCS` Используется однобайтовая кодовая страница.  Если кодовая страница установлена в `_MB_CP_SBCS`, процедуры, подобные [\_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md), всегда возвращают значение false.  
  
-   Любая другая допустимая кодовая страница, независимо от того, является ли значение ANSI, OEM, или другой поддерживаемой операционной системой кодовой страницей \(за исключением UTF\-7 и UTF\-8, которые не поддерживаются\).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_setmbcp`|\<mbctype.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## См. также  
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)