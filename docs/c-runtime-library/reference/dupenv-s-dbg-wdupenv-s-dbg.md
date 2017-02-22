---
title: "_dupenv_s_dbg, _wdupenv_s_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_tdupenv_s_dbg"
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tdupenv_s_dbg - функция"
  - "dupenv_s_dbg - функция"
  - "_wdupenv_s_dbg - функция"
  - "переменные среды"
  - "tdupenv_s_dbg - функция"
  - "wdupenv_s_dbg - функция"
  - "_dupenv_s_dbg - функция"
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# _dupenv_s_dbg, _wdupenv_s_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получают значение из текущей среды.  Версии [\_dupenv\_s, \_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md), которые выделяют память с [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) для предоставления дополнительных сведений об отладке.  
  
## Синтаксис  
  
```  
errno_t _dupenv_s_dbg(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
errno_t _wdupenv_s_dbg(  
   wchar_t **buffer,  
   size_t * numberOfElements,  
   const wchar_t *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### Параметры  
 `buffer`  
 Буфер для хранения значения переменной.  
  
 `numberOfElements`  
 Размер `buffer`.  
  
 `varname`  
 Имя переменной среды.  
  
 `blockType`  
 Запрошенный тип блока памяти: `_CLIENT_BLOCK` или `_NORMAL_BLOCK`.  
  
 `filename`  
 Указатель на имя файла исходного кода или `NULL`.  
  
 `linenumber`  
 Номер строки в файле исходного кода или `NULL`.  
  
## Возвращаемое значение  
 Ноль в случае успеха, код ошибки при сбое.  
  
 Эти функции проверяют свои параметры; если `buffer` или `varname` равно `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают `EINVAL`.  
  
 Если эти функции не могут выделить достаточно памяти, они устанавливают `buffer` в значение `NULL` и `numberOfElements` в значение 0, и возвращают `ENOMEM`.  
  
## Заметки  
 Функции `_dupenv_s_dbg` и `_wdupenv_s_dbg` совпадают с `_dupenv_s` и `_wdupenv_s` за исключением того, что если указано `_DEBUG`, эти функции используют отладочную версию [malloc](../../c-runtime-library/reference/malloc.md), [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md), чтобы выделить память для значения переменной среды.  Дополнительные сведения о возможностях для отладки `_malloc_dbg` см. в разделе [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 В большинстве случаев не нужно вызывать эти функции явно.  Вместо этого можно определить флаг `_CRTDBG_MAP_ALLOC`.  При определенном `_CRTDBG_MAP_ALLOC` вызовы `_dupenv_s` и `_wdupenv_s` отображаются в `_dupenv_s_dbg` и `_wdupenv_s_dbg` соответственно, с `blockType` установленным в `_NORMAL_BLOCK`.  Таким образом, нет необходимости явно вызывать эти функции, если не требуется пометить блоки кучи как `_CLIENT_BLOCK`.  Дополнительные сведения о типах блоков см. в разделе [Типы блоков в отладочной куче](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_dupenv_s_dbg`|\<crtdbg.h\>|  
|`_wdupenv_s_dbg`|\<crtdbg.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_dupenv_s_dbg.c  
#include  <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## Пример результатов выполнения  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## Эквивалент в .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [Константы среды](../../c-runtime-library/environmental-constants.md)   
 [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)