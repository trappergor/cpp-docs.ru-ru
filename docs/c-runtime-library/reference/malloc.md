---
title: "malloc | Microsoft Docs"
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
  - "malloc"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "malloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "malloc - функция"
  - "выделение памяти"
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# malloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет блоки памяти.  
  
## Синтаксис  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### Параметры  
 `size`  
 Байты, которые нужно выделить.  
  
## Возвращаемое значение  
 `malloc` возвращает недействительный указатель в выделенное пространство или `NULL`, если недоступно достаточно памяти.  Чтобы восстановить для указателя тип, отличный от `void`, используйте приведение типа для возвращаемого значения.  Гарантируется, что пространство для хранения, на которое указало возвращенное значение, будет соответствующим образом выровнено для хранения любого типа объекта с требованием о выравнивании менее или равно стандартному выравниванию. \(В Visual C\+\+ основным выравниванием является выравнивание, необходимое для `double` или 8 байт.  В коде, который нацелен на 64\-разрядные платформы, это 16 байт.\) Используйте [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) для выделения памяти для объектов, которые имеют высокие требования к выравниванию — например, типы SSE [\_\_m128](../Topic/__m128.md) и `__m256` и типы, объявляемые с помощью `__declspec(align(``n``))`, где `n` больше 8.  Если значение `size` равно 0, `malloc` выделяет элемент нулевой длины в куче и возвращает допустимый указатель на этот элемент.  Всегда проверяйте возврат из `malloc`, даже если запрашиваемый объем памяти очень мал.  
  
## Заметки  
 Функция `malloc` выделяет блок памяти по крайней мере байтов `size`.  Блок может иметь несколько байтов `size` из\-за пространства, необходимый для выравнивания и данных обслуживания.  
  
 `malloc` задает для параметра `errno` значение `ENOMEM`, если выделение памяти завершается сбоем или количество запрошенной памяти превышает `_HEAP_MAXREQ`.  Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
 Код запуска используется `malloc`, чтобы выделить хранилище для переменных `_environ`, `envp` и `argv`.  Следующие функции и их широкосимвольные аналоги также вызывают `malloc`.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[\_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[функции \_exec](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[\_popen](../../c-runtime-library/reference/popen-wpopen.md)|[функции \_spawn](../Topic/_spawn,%20_wspawn%20Functions.md)|  
|[fgetc](../Topic/fgetc,%20fgetwc.md)|[fsetpos](../Topic/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[\_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[\_fgetchar](../Topic/fgetc,%20fgetwc.md)|[\_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[системный](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../Topic/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[\_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[\_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../Topic/puts,%20_putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[\_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[\_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[\_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../Topic/fputs,%20fputws.md)|[\_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[получает](../../c-runtime-library/gets-getws.md)|[\_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 Функция [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) C\+\+ задает новый режим обработчика события `malloc`.  Указывает, может ли новый режим обработки, при сбое вызова `malloc`, использовать новую процедуру обработчика как набор [\_set\_new\_handler](../Topic/_set_new_handler.md).  По умолчанию `malloc` не вызывает новую процедуру обработчика при сбое выделения памяти.  Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти методом `malloc` метод `malloc` вызывал новую процедуру обработчика таким же образом, как это делает оператор `new` при сбое по той же причине.  Чтобы переопределить значение по умолчанию, вызовите  
  
```cpp  
_set_new_mode(1)  
```  
  
 на ранних этапах программы или компонуйте с использованием NEWMODE.OBJ \(см. [Параметры ссылок](../Topic/Link%20Options.md)\).  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, `malloc` соответствует [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  Дополнительные сведения о том, как происходит управление кучей в процессе отладки см. в разделе [Сведения о куче отладки CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `malloc` помечен `__declspec(noalias)` и `__declspec(restrict)`; это означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним.  Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`malloc`|\<stdlib.h\> и \<malloc.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```c  
// crt_malloc.c  
// This program allocates memory with  
// malloc, then frees the memory with free.  
  
#include <stdlib.h>   // For _MAX_PATH definition  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   char *string;  
  
   // Allocate space for a path name  
   string = malloc( _MAX_PATH );  
  
   // In a C++ file, explicitly cast malloc's return.  For example,   
   // string = (char *)malloc( _MAX_PATH );  
  
   if( string == NULL )  
      printf( "Insufficient memory available\n" );  
   else  
   {  
      printf( "Memory space allocated for path name\n" );  
      free( string );  
      printf( "Memory freed\n" );  
   }  
}  
```  
  
  **Область памяти, выделенная для имени пути**  
**Освобожденная память**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md)