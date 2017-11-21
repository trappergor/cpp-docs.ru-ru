---
title: "malloc | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: malloc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords: malloc
dev_langs: C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72dd949aa8d894ba49f53a6440de20beea070e2b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="malloc"></a>malloc
Размещение блоков памяти  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void *malloc(  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `size`  
 Байты для размещения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функция `malloc` возвращает указатель void на выделенное пространство или значение `NULL`, если памяти недостаточно. Чтобы вернуть указатель на тип, отличный от `void`, используйте приведение типов для возвращаемого значения. Дисковое пространство, на который указывает возвращаемое значение, будет гарантированно соответствовать требованиям к выравниванию для хранения объектов любого типа, если таковые требования не превышают базовые. (В Visual C++ в качестве базовых устанавливаются требования к выравниванию для типа `double` или 8 байтов. В коде для 64-разрядных платформ это ограничение составляет 16 байтов.) Функция [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) выделяет пространство для хранения объектов с более высокими требованиями к выравниванию. Например, это могут быть типы SSE [__m128](../../cpp/m128.md) и `__m256`, а также типы, объявленные с использованием `__declspec(align( n ))`, где `n` больше 8. Если значение `size` равно 0, функция `malloc` выделяет элемент нулевой длины в куче и возвращает допустимый указатель на этот элемент. Всегда проверяйте возвращаемое функцией `malloc` значение, даже если объем запрошенной памяти мал.  
  
## <a name="remarks"></a>Примечания  
 Функция `malloc` выделяет блок памяти размером не менее `size` байтов. Размер блока может превышать `size` байтов из-за дополнительных затрат места на хранение информации о выравнивании и обслуживании.  
  
 Функция `malloc` задает для параметра `errno` в значение `ENOMEM`, если выделение памяти завершается сбоем или количество запрошенной памяти превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Код запуска использует функцию `malloc` для выделения пространства для переменных `_environ`, `envp` и `argv`. Функцию `malloc` также вызывают следующие функции и их аналоги для расширенных символов.  
  
|||||  
|-|-|-|-|  
|[calloc](../../c-runtime-library/reference/calloc.md)|[fscanf](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](../../c-runtime-library/reference/getw.md)|[setvbuf](../../c-runtime-library/reference/setvbuf.md)|  
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)|[_popen](../../c-runtime-library/reference/popen-wpopen.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|  
|[fgetc](../../c-runtime-library/reference/fgetc-fgetwc.md)|[fsetpos](../../c-runtime-library/reference/fsetpos.md)|[printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)|[_strdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)|  
|[_fgetchar](../../c-runtime-library/reference/fgetc-fgetwc.md)|[_fullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)|[putc](../../c-runtime-library/reference/putc-putwc.md)|[system](../../c-runtime-library/reference/system-wsystem.md)|  
|[fgets](../../c-runtime-library/reference/fgets-fgetws.md)|[fwrite](../../c-runtime-library/reference/fwrite.md)|[putchar](../../c-runtime-library/reference/putc-putwc.md)|[_tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|  
|[fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](../../c-runtime-library/reference/getc-getwc.md)|[_putenv](../../c-runtime-library/reference/putenv-wputenv.md)|[ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md)|  
|[fputc](../../c-runtime-library/reference/fputc-fputwc.md)|[getchar](../../c-runtime-library/reference/getc-getwc.md)|[puts](../../c-runtime-library/reference/puts-putws.md)|[vfprintf](../../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|  
|[_fputchar](../../c-runtime-library/reference/fputc-fputwc.md)|[_getcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[_putw](../../c-runtime-library/reference/putw.md)|[vprintf](../../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)|  
|[fputs](../../c-runtime-library/reference/fputs-fputws.md)|[_getdcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)|[scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)||  
|[fread](../../c-runtime-library/reference/fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)||  
  
 Функция [_set_new_mode](../../c-runtime-library/reference/set-new-mode.md) C++ задает новый режим обработчика для `malloc`. Новый режим обработчика указывает, должна ли функция `malloc` при сбое вызывать новую подпрограмму обработчика, заданную функцией [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). По умолчанию в случае, если выделить память не удается, `malloc` не вызывает новую подпрограмму обработчика. Можно переопределить это поведение по умолчанию, чтобы в случае сбоя предоставления памяти функцией `malloc` функция `malloc` вызывала новую подпрограмму обработчика таким же образом, как это делает оператор `new` при сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите `_set_new_mode(1)` ранних этапах программы или связи с NEWMODE. OBJ (см. [параметры Link](../../c-runtime-library/link-options.md)).  
  
 Когда приложение связано с отладочной версией библиотек времени выполнения языка C, функция `malloc` соответствует функции [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
 Функция `malloc` имеет метки `__declspec(noalias)` и `__declspec(restrict)`, что означает, что функция гарантированно не изменит глобальные переменные, а для возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`malloc`|\<stdlib.h> и \<malloc.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```C  
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
  
```Output  
Memory space allocated for path name  
Memory freed  
```  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)
