---
title: _calloc_dbg
ms.date: 11/04/2016
api_name:
- _calloc_dbg
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
- _calloc_dbg
- calloc_dbg
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
ms.openlocfilehash: eab17348e473a4f642e784defe4569e0e799299e
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939321"
---
# <a name="_calloc_dbg"></a>_calloc_dbg

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

*Нумерация*<br/>
Запрошенное число блоков памяти.

*size*<br/>
Запрошенный размер каждого блока памяти (байт).

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

Дополнительные сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения, или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, где была запрошена операция выделения, или **значение NULL**.

Параметры *filename* и *LineNumber* доступны только при явном вызове **_calloc_dbg** или определении константы препроцессора [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) .

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении эта функция возвращает указатель на пользовательскую часть последнего выделенного блока памяти, вызывает новую функцию обработчика или возвращает **значение NULL**. Полное описание поведения возвращения см. в разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [calloc](calloc.md).

## <a name="remarks"></a>Примечания

**_calloc_dbg** — это отладочная версия функции [calloc](calloc.md) . Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_calloc_dbg** уменьшается до вызова **calloc**. **Calloc** и **_calloc_dbg** *выделяют блоки* памяти в базовой куче, но **_calloc_dbg** предлагает несколько функций отладки:

- Буферы с обеих сторон пользовательской части блока, которые необходимо проверить на наличие утечек.

- Параметр типа блока для отслеживания конкретных типов выделения.

- *имя файла*/данных*LineNumber* для определения источника запросов на выделение.

**_calloc_dbg** выделяет каждый блок памяти с немного больше пространства, чем запрошенный *Размер*. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.

**_calloc_dbg** задает **еномем** в случае сбоя выделения памяти; **Еинвал** возвращается, если объем необходимой памяти (включая ранее накладные расходы) превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

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
