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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: afe9264351110bc062d6168ef803fa6fb796538a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341572"
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

*Размер*<br/>
Байты для размещения.

## <a name="return-value"></a>Возвращаемое значение

**malloc** возвращает пустоту указателя в выделенное пространство, или **NULL,** если не хватает памяти. Чтобы вернуть указатель к типу, кроме **недействительного,** используйте тип, отлитый на значении возврата. Дисковое пространство, на который указывает возвращаемое значение, будет гарантированно соответствовать требованиям к выравниванию для хранения объектов любого типа, если таковые требования не превышают базовые. (В визуальном C, фундаментальное выравнивание является выравнивание, которое требуется для **двойного,** или 8 байтов. В коде, который нацелен на 64-битные платформы, это 16 байтов.) Используйте [_aligned_malloc](aligned-malloc.md) для выделения хранилища для объектов, которые имеют более крупное требование выравнивания, например, типы SSE [__m128](../../cpp/m128.md) и **__m256,** а также типы, которые объявляются с помощью, `__declspec(align( n ))` где **n** больше, чем 8. Если *размер* 0, **malloc** выделяет элемент нулевой длины в куче и возвращает действительный указатель на этот элемент. Всегда проверяйте возврат от **malloc**, даже если количество памяти запрошено мало.

## <a name="remarks"></a>Remarks

Функция **malloc** выделяет блок памяти по крайней мере *размера* байтов. Блок может быть больше *байтов размера* из-за пространства, необходимого для сведения о выравнивании и обслуживании.

**malloc** устанавливает **errno** к **ENOMEM** если распределение памяти терпит неудачу или если количество запрошенной памяти превышает **_HEAP_MAXREQ.** Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Код запуска использует **malloc** для распределения хранилища для **переменных _environ,** *envp*и *argv.* Следующие функции и их широкохарактерные аналоги также называют **malloc**.

|||||
|-|-|-|-|
|[calloc](calloc.md)|[fscanf](fscanf-fscanf-l-fwscanf-fwscanf-l.md)|[_getw](getw.md)|[setvbuf](setvbuf.md)|
|[Функции _exec](../../c-runtime-library/exec-wexec-functions.md)|[fseek](fseek-fseeki64.md)|[_popen](popen-wpopen.md)|[Функции _spawn](../../c-runtime-library/spawn-wspawn-functions.md)|
|[fgetc](fgetc-fgetwc.md)|[fsetpos](fsetpos.md)|[printf](printf-printf-l-wprintf-wprintf-l.md)|[_strdup](strdup-wcsdup-mbsdup.md)|
|[_fgetchar](fgetc-fgetwc.md)|[_fullpath](fullpath-wfullpath.md)|[putc](putc-putwc.md)|[система](system-wsystem.md)|
|[fgets](fgets-fgetws.md)|[fwrite](fwrite.md)|[putchar](putc-putwc.md)|[_tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md)|
|[fprintf](fprintf-fprintf-l-fwprintf-fwprintf-l.md)|[getc](getc-getwc.md)|[_putenv](putenv-wputenv.md)|[ungetc](ungetc-ungetwc.md)|
|[fputc](fputc-fputwc.md)|[гетчар](getc-getwc.md)|[puts](puts-putws.md)|[vfprintf](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)|
|[_fputchar](fputc-fputwc.md)|[_getcwd](getcwd-wgetcwd.md)|[_putw](putw.md)|[vprintf](vprintf-vprintf-l-vwprintf-vwprintf-l.md)|
|[fputs](fputs-fputws.md)|[_getdcwd](getcwd-wgetcwd.md)|[scanf](scanf-scanf-l-wscanf-wscanf-l.md)||
|[fread](fread.md)|[gets](../../c-runtime-library/gets-getws.md)|[_searchenv](searchenv-wsearchenv.md)||

Функция [_set_new_mode](set-new-mode.md) C++ задает новый режим обработчика для **malloc**. Новый режим обработчика указывает, является ли, при сбое, **malloc** является вызов новой рутины обработчика, как установить [_set_new_handler.](set-new-handler.md) По умолчанию **malloc** не вызывает новую рутину обработчика при неспособности выделить память. Вы можете переопределить это поведение по умолчанию, так что, когда **malloc** не выделяет память, **malloc** вызывает новую рутину обработчика так же, как **новый** оператор делает, когда он не по той же причине. Чтобы переопределить значение `_set_new_mode(1)` по умолчанию, позвоните в начале программы или свяжитесь с NEWMODE. OBJ (см. [Варианты ссылки).](../../c-runtime-library/link-options.md)

Когда приложение связано с отладкой версии библиотек исправления C, **malloc** решает [_malloc_dbg.](malloc-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

**malloc** отмечен `__declspec(noalias)` `__declspec(restrict)`и ; это означает, что функция гарантированно не изменяет глобальные переменные, и что ответуказатель не псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

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

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[Бесплатный](free.md)<br/>
[realloc](realloc.md)<br/>
[_aligned_malloc](aligned-malloc.md)<br/>
