---
title: _calloc_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _calloc_dbg
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
- _calloc_dbg
- calloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2759c19fb88b820fc346b5cf35e97522b7e74cb6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396775"
---
# <a name="callocdbg"></a>_calloc_dbg

Выделяет ряд блоков памяти в куче с дополнительным пространством для заголовка отладки и буферов перезаписи (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void *_calloc_dbg(
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*Номер*<br/>
Запрошенное число блоков памяти.

*size*<br/>
Запрошенный размер каждого блока памяти (байт).

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

Дополнительные сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения или **NULL**.

*linenumber*<br/>
Номер строки в исходном файле, которой была запрошена операция выделения или **NULL**.

*Filename* и *linenumber* доступны, только если **_calloc_dbg** была явно вызвана или [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)определена константа препроцессора.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении эта функция возвращает указатель на пользовательскую часть последний выделенный блок памяти, вызывает новую функцию обработчика или возвращает **NULL**. Полное описание поведения возвращения см. в разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [calloc](calloc.md).

## <a name="remarks"></a>Примечания

**_calloc_dbg** является отладочной версией [calloc](calloc.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_calloc_dbg** сокращается до вызова **calloc**. Оба **calloc** и **_calloc_dbg** выделить *номер* блоков памяти в основной куче, но **_calloc_dbg** предлагает несколько отладки функции:

- Буферы с обеих сторон пользовательской части блока, которые необходимо проверить на наличие утечек.

- Параметр типа блока для отслеживания конкретных типов выделения.

- *Имя файла*/*linenumber* сведения для определения источника запросов на выделение.

**_calloc_dbg** выделяет каждый блок памяти, добавив немного больше пространства, чем запрошено *размер*. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.

**_calloc_dbg** задает **errno** для **ENOMEM** при сбое выделения памяти; **EINVAL** возвращается, если объем памяти (включая ранее упомянутую нагрузку) превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи см. в статье [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_calloc_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_callocd.c
// This program uses _calloc_dbg to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>
#include <crtdbg.h>

int main( void )
{
    long *bufferN, *bufferC;

    // Call _calloc_dbg to include the filename and line number
    // of our allocation request in the header and also so we can
    // allocate CLIENT type blocks specifically
    bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );
    bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );
    if( bufferN != NULL && bufferC != NULL )
        printf( "Allocated memory successfully\n" );
    else
        printf( "Problem allocating memory\n" );

    / _free_dbg must be called to free CLIENT type blocks
    free( bufferN );
    _free_dbg( bufferC, _CLIENT_BLOCK );
}
```

```Output
Allocated memory successfully
```

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[calloc](calloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
