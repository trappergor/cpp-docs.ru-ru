---
title: "Глобальные переменные | Microsoft Docs"
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
  - "c.variables"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "глобальные переменные"
  - "глобальные переменные, Библиотека времени выполнения Microsoft"
  - "переменные, общие"
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Глобальные переменные
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека времени выполнения языка C \(Майкрософт\) обеспечивает следующие глобальные переменные или макросы.  Многие из этих глобальных переменных или макросов были признаны нерекомендуемыми и заменены более надежными и безопасными функциональными версиями, которые мы рекомендуем использовать вместо них.  
  
|Переменная|Описание|  
|----------------|--------------|  
|[\_\_argc, \_\_argv, \_\_wargv](../c-runtime-library/argc-argv-wargv.md)|Содержит аргументы командной строки.|  
|[\_daylight, \_dstbias, \_timezone и \_tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|Не рекомендуется.  Используйте `_get_daylight`, `_get_dstbias`, `_get_timezone` и `_get_tzname`.<br /><br /> Вносит корректировку для локального времени; используется в некоторых функциях даты и времени.|  
|[errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)|Не рекомендуется.  Используйте `_get_errno`, `_set_errno`, `_get_doserrno`, `_set_doserrno`, `perror` и `strerror`.<br /><br /> Хранит коды ошибок и связанные сведения.|  
|[\_environ, \_wenviron](../c-runtime-library/environ-wenviron.md)|Не рекомендуется.  Используйте `getenv_s`, `_wgetenv_s`, `_dupenv_s`, `_wdupenv_s`, `_putenv_s` и `_wputenv_s`.<br /><br /> Указывает на массив указателей на строки среды процесса; инициализация при запуске.|  
|[\_fmode](../c-runtime-library/fmode.md)|Не рекомендуется.  Используйте `_get_fmode` или `_set_fmode`.<br /><br /> Задает режим преобразования файлов по умолчанию.|  
|[\_iob](../c-runtime-library/iob.md)|Массив структур управления вводом\-выводом для консоли, файлов и устройств.|  
|[\_pctype, \_pwctype, \_wctype, \_mbctype, \_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|Содержит сведения, используемые функциями классификации символов.|  
|[\_pgmptr, \_wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|Не рекомендуется.  Используйте `_get_pgmptr` или `_get_wpgmptr`.<br /><br /> Инициализируется при запуске программы до полного или относительного пути программы, полного имени программы или имени программы без расширения имени файла \(в зависимости от способа вызова программы\).|  
  
## См. также  
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)   
 [\_\_argc, \_\_argv, \_\_wargv](../c-runtime-library/argc-argv-wargv.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [\_get\_doserrno](../Topic/_get_doserrno.md)   
 [\_set\_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [\_get\_errno](../Topic/_get_errno.md)   
 [\_set\_errno](../Topic/_set_errno.md)   
 [\_dupenv\_s, \_wdupenv\_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)