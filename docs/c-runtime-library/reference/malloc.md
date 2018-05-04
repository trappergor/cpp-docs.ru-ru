---
title: malloc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- malloc
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
f1_keywords:
- malloc
dev_langs:
- C++
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f600deb7bfa9b65ed9bdf784f2a16bd037729a51
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="malloc"></a>malloc

Размещение блоков памяти

## <a name="syntax"></a>Синтаксис

```C
void *malloc(
   size_t size
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Байты для размещения.

## <a name="return-value"></a>Возвращаемое значение

**malloc** возвращает указатель void на выделенное пространство или **NULL** Если возникает нехватка памяти. Чтобы вернуть указатель на тип, отличный от **void**, используйте приведение типа для возвращаемого значения. Дисковое пространство, на который указывает возвращаемое значение, будет гарантированно соответствовать требованиям к выравниванию для хранения объектов любого типа, если таковые требования не превышают базовые. (В Visual C++, основные выравнивание — выравнивания, который необходим для **двойные**, или 8 байт. В коде для 64-разрядных платформ это ограничение составляет 16 байтов.) Используйте [_aligned_malloc](aligned-malloc.md) для выделения хранилища для объектов, которые имеют больше требование к выравниванию — например, типов SSE [__m128](../../cpp/m128.md) и **__m256**и типы объявлено с помощью `__declspec(align( n ))` где **n** больше 8. Если *размер* равно 0, **malloc** выделяет элемент нулевой длины в куче и возвращает допустимый указатель к элементу. Всегда проверяйте возвращаемое из **malloc**, даже если объем запрошенной памяти мал.

## <a name="remarks"></a>Примечания

**Malloc** функция выделяет блок памяти, по крайней мере *размер* байт. Блок может быть больше, чем *размер* байт из-за пространство, требуемое для выравнивания и обслуживание сведения.

**malloc** задает **errno** для **ENOMEM** если выделение памяти завершается сбоем или количество запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Использует код запуска **malloc** для выделения хранилища для **_environ**, *envp*, и *argv* переменных. Следующие функции и их аналогами двухбайтовые также вызвать **malloc**.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[system](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

Функция [_set_new_mode](set-new-mode.md) C++ задает новый режим обработчика для **malloc**. Новый режим обработки указывает, что в случае сбоя **malloc** является вызов новую подпрограмму обработчика задается [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывать новую подпрограмму обработчика сбои при выделении памяти. Можно переопределить это поведение по умолчанию, чтобы, когда **malloc** не удается выделить память, **malloc** вызывает новую подпрограмму обработчика так же, как **новый** делает оператор При сбое по той же причине. Чтобы переопределить значение по умолчанию, вызовите `_set_new_mode(1)` ранних этапах программы или связи с NEWMODE. OBJ (см. [параметры Link](../../c-runtime-library/link-options.md)).

Когда приложение связано с отладочной версией библиотеки времени выполнения C **malloc** разрешается [_malloc_dbg](malloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**malloc** помечен `__declspec(noalias)` и `__declspec(restrict)`; это означает, что функция гарантированно не изменит глобальные переменные и возвращаемого указателя не будет создан псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**malloc**|\<stdlib.h> и \<malloc.h>|

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

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
