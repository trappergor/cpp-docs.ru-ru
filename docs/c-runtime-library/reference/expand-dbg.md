---
title: _expand_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _expand_dbg
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
apitype: DLLExport
f1_keywords:
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b8fc9db941700542d82b2a1a1449aafc0375fbf6
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="expanddbg"></a>_expand_dbg

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

*Устойчивость данных пользователя*<br/>
Указатель на ранее выделенный блок памяти.

*newSize*<br/>
Запрашиваемый новый размер для блока (в байтах).

*blockType*<br/>
Запрашиваемый тип для блока с измененным размером: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию расширения или **NULL**.

*linenumber*<br/>
Номер строки в исходном файле, которой была запрошена операция расширения или **NULL**.

*Filename* и *linenumber* доступны, только если **_expand_dbg** была явно вызвана или [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)определена константа препроцессора.

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении **_expand_dbg** возвращает указатель на блок памяти с измененным размером. Поскольку память не перемещается, адрес совпадает с userData. Если произошла ошибка или блок не удалось расширить до запрашиваемого размера, он возвращает **NULL**. В случае сбоя **errno** содержит сведения из операционной системы о причине сбоя. Дополнительные сведения о **errno**, в разделе [errno _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

**_Expand_dbg** функция является отладочной версией функции _[разверните](expand.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_expand_dbg** сокращается до вызова **ра_сширить сайт**. Оба **ра_сширить сайт** и **_expand_dbg** изменяет размер блока памяти в основной куче, но **_expand_dbg** включает различные функции отладки: буферы на обеих сторонах пользователя части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, и *filename*/*linenumber* сведения для определения источника запросов на выделение.

**_expand_dbg** размера указанный блок памяти немного больше места, чем запрошено *newSize*. *newSize* может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Изменение размера достигается либо расширением, либо сжатием исходного блока памяти. **_expand_dbg** не перемещает блок памяти, как и в [_realloc_dbg](realloc-dbg.md) функции.

Когда *newSize* больше, чем исходный блок размера, блок памяти расширяется. При расширении, если блок памяти нельзя увеличить до запрошенного размера **NULL** возвращается. Когда *newSize* меньше, чем исходный блок размер блока памяти сжимается до достижения нового размера.

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

Эта функция проверяет свои параметры. Если *memblock* является пустым указателем, или если размер больше, чем **_HEAP_MAXREQ**, эта функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает **NULL**.

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
