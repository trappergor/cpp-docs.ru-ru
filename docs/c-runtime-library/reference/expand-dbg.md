---
title: _expand_dbg
ms.date: 11/04/2016
api_name:
- _expand_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- expand_dbg
- _expand_dbg
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
ms.openlocfilehash: 836b9cffcf0367f248a14469b30c1a355e2bdec2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941580"
---
# <a name="_expand_dbg"></a>_expand_dbg

Изменяет размер указанного блока памяти в куче путем его расширения или сжатия (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void *_expand_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*userData*<br/>
Указатель на ранее выделенный блок памяти.

*newSize*<br/>
Запрашиваемый новый размер для блока (в байтах).

*blockType*<br/>
Запрошенный тип для блока с измененным размером: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию расширения, или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция расширения, или **значение NULL**.

Параметры *filename* и *LineNumber* доступны только при явном вызове **_expand_dbg** или определении константы препроцессора [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) .

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_expand_dbg** возвращает указатель на блок памяти с измененным размером. Поскольку память не перемещается, адрес совпадает с userData. Если произошла ошибка или не удалось расширить блок до запрошенного размера, возвращается **значение NULL**. В **случае сбоя** система пересекается с информацией операционной системы о характере сбоя. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr".

## <a name="remarks"></a>Примечания

Функция **_expand_dbg** является отладочной версией функции _[expand](expand.md) . Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_expand_dbg** уменьшается до вызова **_expand**. И **_expand** , и **_expand_dbg** изменяют размер блока памяти в базовой куче, но **_expand_dbg** поддерживает несколько функций отладки: буферы с обеих сторон пользовательской части блока для проверки утечек, параметр типа блока для трассировки. конкретные типы распределения и сведения о *filename*/*LineNumber* для определения источника запросов на выделение.

**_expand_dbg** изменяет размер указанного блока памяти, дополнив немного больше пространства, чем запрошенное *newSize*. *newSize* может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Изменение размера достигается либо расширением, либо сжатием исходного блока памяти. **_expand_dbg** не перемещает блок памяти, как и функция [_realloc_dbg](realloc-dbg.md) .

Если *newSize* больше, чем исходный размер блока, блок памяти разворачивается. Если в процессе расширения блок памяти не может быть расширен в соответствии с требуемым размером, возвращается **значение NULL** . Если *newSize* меньше, чем исходный размер блока, то блок памяти продается по контракту, пока не будет получен новый размер.

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Эта функция проверяет свои параметры. Если *мемблокк* является пустым указателем или size больше **_HEAP_MAXREQ**, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено **, для** параметра **еинвал** устанавливается значение, а функция возвращает **значение NULL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>Комментарий

Вывод этой программы зависит от того, способен ли ваш компьютер расширить все разделы. Если все разделы развернуты, результат отражается в секции вывода.

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
