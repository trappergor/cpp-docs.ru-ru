---
title: malloc
ms.date: 4/2/2020
api_name:
- malloc
- _o_malloc
api_location:
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- malloc
helpviewer_keywords:
- malloc function
- memory allocation
ms.assetid: 144fcee2-be34-4a03-bb7e-ed6d4b99eea0
ms.openlocfilehash: 4e699920f37139be40542ba91b3740cd9edef148
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917513"
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

Функция **malloc** возвращает указатель void на выделенное пространство или **значение NULL** , если объем доступной памяти недостаточен. Чтобы получить указатель на тип, отличный от **void**, используйте приведение типа к возвращаемому значению. Дисковое пространство, на который указывает возвращаемое значение, будет гарантированно соответствовать требованиям к выравниванию для хранения объектов любого типа, если таковые требования не превышают базовые. (В Visual C++ основное выравнивание — это выравнивание, требуемое для **Double**или 8 байт. В коде, ориентированном на 64-разрядные платформы, это 16 байт.) Используйте [_aligned_malloc](aligned-malloc.md) , чтобы выделить хранилище для объектов с более высоким требованием выравнивания, например типы SSE [__m128](../../cpp/m128.md) и **__m256**, и типы, объявленные с помощью `__declspec(align( n ))` , где **n** больше 8. Если *Размер* равен 0, функция **malloc** выделяет элемент нулевой длины в куче и возвращает допустимый указатель на этот элемент. Всегда проверяйте возврат от **malloc**, даже если требуемый объем памяти мал.

## <a name="remarks"></a>Remarks

Функция **malloc** выделяет блок *памяти размером не меньше байт.* Блок может быть больше, чем *Размер* байтов, из-за пространства, необходимого для выравнивания и сведений об обслуживании.

**malloc** **переводится** в **еномем** , если выделение памяти завершается ошибкой или объем запрошенной памяти превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Код запуска использует **malloc** для выделения памяти для переменных **_environ**, *envp*и *argv* . Следующие функции и их аналоги в расширенных символах также вызывают функцию **malloc**.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[система](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[getchar](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[получение](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

Функция [_set_new_mode](set-new-mode.md) C++ задает новый режим обработчика для **malloc**. Новый режим обработчика указывает, что в случае сбоя **malloc** вызывает новую подпрограммы обработчика, заданную [_set_new_handler](set-new-handler.md). По умолчанию **malloc** не вызывает новую подпрограммы обработчика при сбое выделения памяти. Это поведение по умолчанию можно переопределить таким образом, что, когда **malloc** не сможет выделить память, **malloc** вызывает новую подпрограммы обработчика так же, как и оператор **New** в случае сбоя по той же причине. Чтобы переопределить значение по умолчанию `_set_new_mode(1)` , вызовите на раннем этапе программы или СВЯЖИТЕ с использованием NEWMODE. OBJ (см. раздел [Параметры связи](../../c-runtime-library/link-options.md)).

Если приложение связано с отладочной версией библиотек времени выполнения C, **malloc** разрешается в [_malloc_dbg](malloc-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**malloc** помечен `__declspec(noalias)` и `__declspec(restrict)`; Это означает, что функция гарантированно не изменяет глобальные переменные и что возвращаемый указатель не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**malloc**|\<stdlib.h> и \<malloc.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[свободный](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
