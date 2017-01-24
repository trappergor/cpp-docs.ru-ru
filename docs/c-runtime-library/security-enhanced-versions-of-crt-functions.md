---
title: "Версии функций CRT повышенной безопасности | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "CRT - библиотека, усовершенствования безопасности"
  - "безопасность [CRT]"
  - "CRT с повышенным уровнем безопасности"
ms.assetid: f87e5a01-4cb2-4379-9e8f-d4693828c55a
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Версии функций CRT повышенной безопасности
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Доступны более безопасные версии подпрограмм библиотеки среды выполнения. Дополнительные сведения об усовершенствованиях безопасности в CRT см. в статье [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
 **Безопасные функции**  
  
|Функция CRT|Функция с усиленной безопасностью|Применение|  
|-----------------|---------------------------------------|----------------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md)|[\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|Определяют разрешения на доступ к файлам|  
|[\_alloca](../c-runtime-library/reference/alloca.md)|[\_malloca](../c-runtime-library/reference/malloca.md)|Выделение памяти в стеке|  
|[asctime, \_wasctime](../c-runtime-library/reference/asctime-wasctime.md)|[asctime\_s, \_wasctime\_s](../c-runtime-library/reference/asctime-s-wasctime-s.md)|Преобразуют время из типа `struct tm` в символьную строку.|  
|[bsearch](../c-runtime-library/reference/bsearch.md)|[bsearch\_s](../c-runtime-library/reference/bsearch-s.md)|Выполнение двоичного поиска по отсортированному массиву|  
|Устаревшая функция|[\_cgets\_s, \_cgetws\_s](../Topic/_cgets_s,%20_cgetws_s.md)|Возвращают строку символов из консоли|  
|[\_chsize](../c-runtime-library/reference/chsize.md)|[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|Изменяет размер файла|  
|[clearerr](../c-runtime-library/reference/clearerr.md)|[clearerr\_s](../c-runtime-library/reference/clearerr-s.md)|Сбрасывает индикатор ошибок для потока|  
|[\_control87, \_controlfp, \_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)|[\_controlfp\_s](../c-runtime-library/reference/controlfp-s.md)|Возвращает и задает управляющее слово блока операций с плавающей запятой|  
|[\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)|[\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Форматирует данные и печатает их в консоли|  
|[\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)|[\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Считывает отформатированные данные из консоли|  
|[ctime, \_ctime32, \_ctime64, \_wctime, \_wctime32, \_wctime64](../c-runtime-library/reference/ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)|[\_ctime\_s, \_ctime32\_s, \_ctime64\_s, \_wctime\_s, \_wctime32\_s, \_wctime64\_s](../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)|Преобразуют время из типа `time_t`, `__time32_t` или `__time64_t` в символьную строку|  
|[\_ecvt](../c-runtime-library/reference/ecvt.md)|[\_ecvt\_s](../Topic/_ecvt_s.md)|Преобразует число `double` в строку|  
|[\_fcvt](../Topic/_fcvt.md)|[\_fcvt\_s](../c-runtime-library/reference/fcvt-s.md)|Преобразует число с плавающей запятой в строку|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)|[fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Открывают файл|  
|[fprintf, \_fprintf\_l, fwprintf, \_fwprintf\_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[fprintf\_s, \_fprintf\_s\_l, fwprintf\_s, \_fwprintf\_s\_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Выводят форматированные данные в поток|  
|[fread](../c-runtime-library/reference/fread.md)|[fread\_s](../c-runtime-library/reference/fread-s.md)|Считывает данные из файла|  
|[\_fread\_nolock](../c-runtime-library/reference/fread-nolock.md)|[\_fread\_nolock\_s](../Topic/_fread_nolock_s2.md)|Считывает данные из файла без использования блокировки многопотоковой записи|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)|[freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Повторно открывает файл|  
|[fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Считывают форматированные данные из потока|  
|[\_ftime, \_ftime32, \_ftime64](../c-runtime-library/reference/ftime-ftime32-ftime64.md)|[\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../Topic/_ftime_s,%20_ftime32_s,%20_ftime64_s.md)|Отображают текущее время|  
|[\_gcvt](../c-runtime-library/reference/gcvt.md)|[\_gcvt\_s](../c-runtime-library/reference/gcvt-s.md)|Преобразует значение с плавающей запятой в строку и сохраняет ее в буфер|  
|[getenv, \_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)|[getenv\_s, \_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)|Получают значение из текущей среды.|  
|Устаревшая функция|[gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md)|Получают строку из потока `stdin`|  
|[gmtime, \_gmtime32, \_gmtime64](../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)|[\_gmtime32\_s, \_gmtime64\_s](../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)|Преобразует время из типа `time_t` в тип `struct``tm` или из типа `__time64_t` в тип `struct tm`|  
|[\_itoa, \_i64toa, \_ui64toa, \_itow, \_i64tow, \_ui64tow](../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md)|[\_itoa\_s, \_i64toa\_s, \_ui64toa\_s, \_itow\_s, \_i64tow\_s, \_ui64tow\_s](../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)|Преобразуют целое число в строку|  
|[\_lfind](../c-runtime-library/reference/lfind.md)|[\_lfind\_s](../Topic/_lfind_s.md)|Выполняет линейный поиск указанного ключа|  
|[localtime, \_localtime32, \_localtime64](../c-runtime-library/reference/localtime-localtime32-localtime64.md)|[localtime\_s, \_localtime32\_s, \_localtime64\_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)|Преобразует время из типа `time_t` в тип `struct tm` или из типа `__time64_t` в тип `struct tm`с поправкой на местное время|  
|[\_lsearch](../c-runtime-library/reference/lsearch.md)|[\_lsearch\_s](../c-runtime-library/reference/lsearch-s.md)|Выполняет линейный поиск значения и добавляет значение в конец списка, если оно не найдено|  
|[\_ltoa, \_ltow](../Topic/_ltoa,%20_ltow.md)|[\_ltoa\_s, \_ltow\_s](../c-runtime-library/reference/ltoa-s-ltow-s.md)|Преобразует целое число типа long в строку|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md)|[\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|Создают путь из компонентов|  
|[\_mbccpy, \_mbccpy\_l](../Topic/_mbccpy,%20_mbccpy_l.md)|[\_mbccpy\_s, \_mbccpy\_s\_l](../c-runtime-library/reference/mbccpy-s-mbccpy-s-l.md)|Копирует многобайтовый символ из одной строки в другую|  
|[\_mbsnbcat, \_mbsnbcat\_l](../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)|[\_mbsnbcat\_s, \_mbsnbcat\_s\_l](../Topic/_mbsnbcat_s,%20_mbsnbcat_s_l.md)|Добавляет первые байты \(не более `n`\) одной многобайтовой строки к другой|  
|[\_mbsnbcpy, \_mbsnbcpy\_l](../Topic/_mbsnbcpy,%20_mbsnbcpy_l.md)|[\_mbsnbcpy\_s, \_mbsnbcpy\_s\_l](../c-runtime-library/reference/mbsnbcpy-s-mbsnbcpy-s-l.md)|Копирует байты \(`n`\) строки в целевую строку|  
|[\_mbsnbset, \_mbsnbset\_l](../c-runtime-library/reference/mbsnbset-mbsnbset-l.md)|[\_mbsnbset\_s, \_mbsnbset\_s\_l](../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)|Устанавливает для первых байтов \(`n`\) строки значение указанного символа|  
|[mbsrtowcs](../c-runtime-library/reference/mbsrtowcs.md)|[mbsrtowcs\_s](../c-runtime-library/reference/mbsrtowcs-s.md)|Преобразует строку многобайтовых символов в строку соответствующих расширенных символов|  
|[mbstowcs, \_mbstowcs\_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)|[mbstowcs\_s, \_mbstowcs\_s\_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|Преобразует последовательность многобайтовых символов в соответствующую последовательность расширенных символов|  
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|[memcpy\_s, wmemcpy\_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Копирует символы из одного буфера в другой|  
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md)|[memmove\_s, wmemmove\_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Перемещает один буфер в другой|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md)|[\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|Создают уникальное имя файла|  
|[printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[printf\_s, \_printf\_s\_l, wprintf\_s, \_wprintf\_s\_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Выводят форматированные выходные данные в стандартный выходной поток|  
|[\_putenv, \_wputenv](../c-runtime-library/reference/putenv-wputenv.md)|[\_putenv\_s, \_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)|Создают, изменяют или удаляют переменные среды|  
|[qsort](../c-runtime-library/reference/qsort.md)|[qsort\_s](../c-runtime-library/reference/qsort-s.md)|Выполняет быструю сортировку|  
|[rand](../Topic/rand.md)|[rand\_s](../c-runtime-library/reference/rand-s.md)|Создает псевдослучайное число|  
|[scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)|[scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Считывают форматированные данные из стандартного входного потока|  
|[\_searchenv, \_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md)|[\_searchenv\_s, \_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)|Ищут файл, используя пути в среде|  
|[snprintf, \_snprintf, \_snprintf\_l, \_snwprintf, \_snwprintf\_l](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)|[\_snprintf\_s, \_snprintf\_s\_l, \_snwprintf\_s, \_snwprintf\_s\_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Записывают форматированных данных в строку|  
|[\_snscanf, \_snscanf\_l, \_snwscanf, \_snwscanf\_l](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md)|[\_snscanf\_s, \_snscanf\_s\_l, \_snwscanf\_s, \_snwscanf\_s\_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Считывают форматированные данные указанной длины из строки|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)|[\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|Открывают файл для общего доступа|  
|[\_splitpath, \_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)|[\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|Разбивают имя пути на компоненты|  
|[sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)|[sprintf\_s, \_sprintf\_s\_l, swprintf\_s, \_swprintf\_s\_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Записывают форматированных данных в строку|  
|[sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)|[sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)|Считывают форматированные данные из строки|  
|[strcat, wcscat, \_mbscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|[strcat\_s, wcscat\_s, \_mbscat\_s](../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)|Добавляют строку|  
|[strcpy, wcscpy, \_mbscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|[strcpy\_s, wcscpy\_s, \_mbscpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)|Копируют строку|  
|[\_strdate, \_wstrdate](../c-runtime-library/reference/strdate-wstrdate.md)|[\_strdate\_s, \_wstrdate\_s](../c-runtime-library/reference/strdate-s-wstrdate-s.md)|Возвращают текущую системную дату в виде строки|  
|[strerror, \_strerror, \_wcserror, \_\_wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)|[strerror\_s, \_strerror\_s, \_wcserror\_s, \_\_wcserror\_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|Получает системное сообщение об ошибке \(`strerror`, `_wcserror`\) или выводит указанное пользователем сообщение об ошибке \(`_strerror`, `__wcserror`\)|  
|[\_strlwr, \_wcslwr, \_mbslwr, \_strlwr\_l, \_wcslwr\_l, \_mbslwr\_l](../Topic/_strlwr,%20_wcslwr,%20_mbslwr,%20_strlwr_l,%20_wcslwr_l,%20_mbslwr_l.md)|[\_strlwr\_s, \_strlwr\_s\_l, \_mbslwr\_s, \_mbslwr\_s\_l, \_wcslwr\_s, \_wcslwr\_s\_l](../c-runtime-library/reference/strlwr-s-strlwr-s-l-mbslwr-s-mbslwr-s-l-wcslwr-s-wcslwr-s-l.md)|Преобразуют строку в нижний регистр|  
|[strncat, \_strncat\_l, wcsncat, \_wcsncat\_l, \_mbsncat, \_mbsncat\_l](../c-runtime-library/reference/strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|[strncat\_s, \_strncat\_s\_l, wcsncat\_s, \_wcsncat\_s\_l, \_mbsncat\_s, \_mbsncat\_s\_l](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)|Присоединяют символы к строке|  
|[strncpy, \_strncpy\_l, wcsncpy, \_wcsncpy\_l, \_mbsncpy, \_mbsncpy\_l](../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)|[strncpy\_s, \_strncpy\_s\_l, wcsncpy\_s, \_wcsncpy\_s\_l, \_mbsncpy\_s, \_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)|Копируют символы одной строки в другую|  
|[\_strnset, \_strnset\_l, \_wcsnset, \_wcsnset\_l, \_mbsnset, \_mbsnset\_l](../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)|[\_strnset\_s, \_strnset\_s\_l, \_wcsnset\_s, \_wcsnset\_s\_l, \_mbsnset\_s, \_mbsnset\_s\_l](../c-runtime-library/reference/strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md)|Устанавливает для первых символов строки \(n\) значение указанного символа|  
|[\_strset, \_strset\_l, \_wcsset, \_wcsset\_l, \_mbsset, \_mbsset\_l](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[\_strset\_s, \_strset\_s\_l, \_wcsset\_s, \_wcsset\_s\_l, \_mbsset\_s, \_mbsset\_s\_l](../Topic/_strset_s,%20_strset_s_l,%20_wcsset_s,%20_wcsset_s_l,%20_mbsset_s,%20_mbsset_s_l.md)|Устанавливает для всех символов строки значение указанного символа|  
|[\_strtime, \_wstrtime](../Topic/_strtime,%20_wstrtime.md)|[\_strtime\_s, \_wstrtime\_s](../c-runtime-library/reference/strtime-s-wstrtime-s.md)|Возвращают текущее системное время в виде строки|  
|[strtok, \_strtok\_l, wcstok, \_wcstok\_l, \_mbstok, \_mbstok\_l](../Topic/strtok,%20_strtok_l,%20wcstok,%20_wcstok_l,%20_mbstok,%20_mbstok_l.md)|[strtok\_s, \_strtok\_s\_l, wcstok\_s, \_wcstok\_s\_l, \_mbstok\_s, \_mbstok\_s\_l](../c-runtime-library/reference/strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)|Находят следующий токен в строке, используя текущий или переданный языковой стандарт|  
|[\_strupr, \_strupr\_l, \_mbsupr, \_mbsupr\_l, \_wcsupr\_l, \_wcsupr](../c-runtime-library/reference/strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md)|[\_strupr\_s, \_strupr\_s\_l, \_mbsupr\_s, \_mbsupr\_s\_l, \_wcsupr\_s, \_wcsupr\_s\_l](../c-runtime-library/reference/strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md)|Преобразуют строку в верхний регистр|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md)|[tmpfile\_s](../Topic/tmpfile_s.md)|Создает временный файл|  
|[\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|[tmpnam\_s, \_wtmpnam\_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Формирует имена, которые можно использовать для создания временных файлов|  
|[\_ultoa, \_ultow](../c-runtime-library/reference/ultoa-ultow.md)|[\_ultoa\_s, \_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)|Преобразуют целое число типа long в строку|  
|[\_umask](../c-runtime-library/reference/umask.md)|[\_umask\_s](../Topic/_umask_s.md)|Задает маску разрешений файла по умолчанию|  
|[\_vcprintf, \_vcprintf\_l, \_vcwprintf, \_vcwprintf\_l](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md)|[\_vcprintf\_s, \_vcprintf\_s\_l, \_vcwprintf\_s, \_vcwprintf\_s\_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Записывают форматированные выходные данные в консоль с помощью указателя на список аргументов|  
|[vfprintf, \_vfprintf\_l, vfwprintf, \_vfwprintf\_l](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|[vfprintf\_s, \_vfprintf\_s\_l, vfwprintf\_s, \_vfwprintf\_s\_l](../Topic/vfprintf_s,%20_vfprintf_s_l,%20vfwprintf_s,%20_vfwprintf_s_l.md)|Записывают форматированные выходные данные с помощью указателя на список аргументов|  
|[vfscanf, vfwscanf](../c-runtime-library/reference/vfscanf-vfwscanf.md)|[vfscanf\_s, vfwscanf\_s](../c-runtime-library/reference/vfscanf-s-vfwscanf-s.md)|Считывают форматированные данные из потока|  
|[vprintf, \_vprintf\_l, vwprintf, \_vwprintf\_l](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|[vprintf\_s, \_vprintf\_s\_l, vwprintf\_s, \_vwprintf\_s\_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|Записывают форматированные выходные данные с помощью указателя на список аргументов|  
|[vscanf, vwscanf](../c-runtime-library/reference/vscanf-vwscanf.md)|[vscanf\_s, vwscanf\_s](../c-runtime-library/reference/vscanf-s-vwscanf-s.md)|Считывают форматированные данные из стандартного входного потока|  
|[vsnprintf, \_vsnprintf, \_vsnprintf\_l, \_vsnwprintf, \_vsnwprintf\_l](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md)|[vsnprintf\_s, \_vsnprintf\_s, \_vsnprintf\_s\_l, \_vsnwprintf\_s, \_vsnwprintf\_s\_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Записывают форматированные выходные данные с помощью указателя на список аргументов|  
|[vsprintf, \_vsprintf\_l, vswprintf, \_vswprintf\_l, \_\_vswprintf\_l](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md)|[vsprintf\_s, \_vsprintf\_s\_l, vswprintf\_s, \_vswprintf\_s\_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Записывают форматированные выходные данные с помощью указателя на список аргументов|  
|[vsscanf, vswscanf](../c-runtime-library/reference/vsscanf-vswscanf.md)|[vsscanf\_s, vswscanf\_s](../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)|Считывают форматированные данные из строки|  
|[wcrtomb](../c-runtime-library/reference/wcrtomb.md)|[wcrtomb\_s](../c-runtime-library/reference/wcrtomb-s.md)|Преобразует расширенный символ в соответствующее представление многобайтового символа|  
|[wcsrtombs](../c-runtime-library/reference/wcsrtombs.md)|[wcsrtombs\_s](../c-runtime-library/reference/wcsrtombs-s.md)|Преобразует строку расширенных символов в соответствующее представление многобайтовой строки|  
|[wcstombs, \_wcstombs\_l](../Topic/wcstombs,%20_wcstombs_l.md)|[wcstombs\_s, \_wcstombs\_s\_l](../Topic/wcstombs_s,%20_wcstombs_s_l.md)|Преобразует последовательность расширенных символов в соответствующую последовательность многобайтовых символов|  
|[wctomb, \_wctomb\_l](../c-runtime-library/reference/wctomb-wctomb-l.md)|[wctomb\_s, \_wctomb\_s\_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|Преобразует расширенный символ в соответствующий многобайтовый символ|  
  
## См. также  
 [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)