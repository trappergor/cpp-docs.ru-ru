---
title: _realloc_dbg
ms.date: 11/04/2016
api_name:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
ms.openlocfilehash: 58d12ed6f4b013996f3f59cba1b146b823adbee6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949515"
---
# <a name="_realloc_dbg"></a>_realloc_dbg

Перераспределяет указанный блок памяти в куче, перемещая его и (или) изменяя его размер (только для отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
void *_realloc_dbg(
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
Запрошенный размер повторно выделенного блока (в байтах).

*blockType*<br/>
Запрошенный тип для перераспределенного блока: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию **перераспределения** или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция **перераспределения** , или **значение NULL**.

Параметры *filename* и *LineNumber* доступны только при явном вызове **_realloc_dbg** или определении константы препроцессора [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) .

## <a name="return-value"></a>Возвращаемое значение

При успешном завершении эта функция либо возвращает указатель на пользовательскую часть перераспределенного блока памяти, вызывает новую функцию обработчика, либо возвращает **значение NULL**. Полное описание поведения возвращения см. в следующем разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [realloc](realloc.md).

## <a name="remarks"></a>Примечания

**_realloc_dbg** — это отладочная версия функции [realloc](realloc.md) . Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_realloc_dbg** уменьшается до вызова метода **realloc**. Как **перераспределение, так** и **_realloc_dbg** перераспределяют блок памяти в базовой куче, но **_realloc_dbg** поддерживает несколько функций отладки: буферы с обеих сторон пользовательской части блока для проверки утечек, параметр типа блока для Следите за конкретными типами распределения*и сведениями* о файле *filename*/, чтобы определить происхождение запросов на выделение.

**_realloc_dbg** перераспределяет указанный блок памяти с немного больше пространства, чем запрошенный *newSize*. *newSize* может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти. Если блок памяти перемещен, содержимое исходного блока перезаписывается.

**_realloc_dbg** устанавливает **значение** переводится в **еномем** , если выделение памяти завершается ошибкой или объем необходимой памяти (включая ранее загруженные издержки) превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_realloc_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

См. пример в разделе [_msize_dbg](msize-dbg.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
