---
title: "_splitpath_s, _wsplitpath_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsplitpath_s"
  - "_splitpath_s"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wsplitpath_s"
  - "splitpath_s"
  - "_splitpath_s"
  - "wsplitpath_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_splitpath_s - функция"
  - "_wsplitpath_s - функция"
  - "имена путей"
  - "имена путей"
  - "splitpath_s - функция"
  - "wsplitpath_s - функция"
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _splitpath_s, _wsplitpath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Разбивает путь на компоненты.  Здесь представлены версии [\_splitpath, \_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### Параметры  
 \[входящий\] `path`  
 Полный путь.  
  
 \[исходящий\] `drive`  
 Буква диска с двоеточием \(`:`\).  Можно передать `NULL` для этого параметра, если не требуется буква диска.  
  
 \[входящий\] `driveNumberOfElements`  
 Размер буфера `drive` однобайтовых или расширенных символов.  Если `drive` — `NULL`, это значение должно быть 0.  
  
 \[исходящий\] `dir`  
 Путь к каталогу, включая косую черту.  Могут использоваться символы косой черты \( `/` \), обратной косой черты \( `\` \) или оба.  Можно передать `NULL` для этого параметра, если не требуется путь к папке.  
  
 \[входящий\] `dirNumberOfElements`  
 Размер буфера `dir` однобайтовых или расширенных символов.  Если `dir` — `NULL`, это значение должно быть 0.  
  
 \[исходящий\] `fname`  
 Базовое имя файла \(без расширения\).  Можно передать `NULL` для этого параметра, если не требуется имя файла.  
  
 \[входящий\] `nameNumberOfElements`  
 Размер буфера `fname` однобайтовых или расширенных символов.  Если `fname` — `NULL`, это значение должно быть 0.  
  
 \[исходящий\] `ext`  
 Расширение имени файла, включая ведущую точку \(**.**\). Можно передать `NULL` для данного параметра, если расширение имени файла не требуется.  
  
 \[входящий\] `extNumberOfElements`  
 Размер буфера `ext` однобайтовых или расширенных символов.  Если `ext` — `NULL`, это значение должно быть 0.  
  
## Возвращаемое значение  
 Нуль, если успешно; код ошибки при неудаче.  
  
### Условия возникновения ошибки  
  
|Условие|Возвращаемое значение|  
|-------------|---------------------------|  
|Параметр `path` имеет значение `NULL`|`EINVAL`|  
|`drive` — `NULL`, `driveNumberOfElements` отлично от нуля|`EINVAL`|  
|`drive` не `NULL`, `driveNumberOfElements` равно нулю|`EINVAL`|  
|`dir` — `NULL`, `dirNumberOfElements` отлично от нуля|`EINVAL`|  
|`dir` не `NULL`, `dirNumberOfElements` равно нулю|`EINVAL`|  
|`fname` — `NULL`, `nameNumberOfElements` отлично от нуля|`EINVAL`|  
|`fname` не `NULL`, `nameNumberOfElements` равно нулю|`EINVAL`|  
|`ext` — `NULL`, `extNumberOfElements` отлично от нуля|`EINVAL`|  
|`ext` не `NULL`, `extNumberOfElements` равно нулю|`EINVAL`|  
  
 Если срабатывает какое\-либо из приведенных условий, то вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
 Если какой\-либо из этих буферов слишком мал для хранения результата, эти функции очищают все буферы, присваивают им пустые строки, устанавливают `errno` в `ERANGE` и возвращают `ERANGE`.  
  
## Заметки  
 Функция `_splitpath_s`  разделяет путь на его четыре компонента.  `_splitpath_s` автоматически обрабатывает аргументы в виде многобайтовых строк как подходящие, распознавая многобайтовые последовательности символов в соответствии с текущей многобайтовой кодовой страницей.  `_wsplitpath_s`  — это расширенная версия `_splitpath_s`; аргументы для `_``wsplitpath_s` ``  представляют собой расширенные строки.  В остальном эти функции ведут себя идентично.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Каждый компонент полного пути хранится в отдельном буфере; константы манифеста `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` и `_MAX_EXT` \(определены в STDLIB.H\) определяют максимальный допустимый размер каждого компонента файла.  Компоненты файла, размер которых превышает соответствующие константы манифеста, могут вызвать повреждение кучи.  
  
 В приведенной ниже таблице перечислены значения констант манифеста.  
  
|Имя|Значение|  
|---------|--------------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 Если полный путь не содержит компонент \(например, имя файла\), то `_splitpath_s` присваивает пустую строку соответствующему буферу.  
  
 В C\+\+ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size.  Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../Topic/Secure%20Template%20Overloads.md).  
  
 Отладочные версии этих функций сначала заполняют буфер значением 0xFD.  Для отключения данного поведения используйте [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_splitpath_s`|\<stdlib.h\>|  
|`_wsplitpath_s`|\<stdlib.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
 См. пример в разделе [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [\_splitpath, \_wsplitpath](../Topic/_splitpath,%20_wsplitpath.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)