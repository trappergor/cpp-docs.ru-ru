---
title: _aligned_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_malloc_dbg
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
- _aligned_malloc_dbg
- aligned_malloc_dbg
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
ms.openlocfilehash: 4fc6789e5fecda38678052c7e805728a49219bc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631876"
---
# <a name="alignedmallocdbg"></a>_aligned_malloc_dbg

Выделяет память в указанных границах выравнивания с дополнительным пространством для заголовка отладки и буферов перезаписи (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_malloc_dbg(
    size_t size,
    size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Размер запрошенного размещения памяти.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения, или NULL.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция выделения, или NULL.

## <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, которая была выделена или значение NULL, если произошел сбой операции.

## <a name="remarks"></a>Примечания

**_aligned_malloc_dbg** является отладочной версией [_aligned_malloc](aligned-malloc.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_aligned_malloc_dbg** сокращается до вызова `_aligned_malloc`. Оба `_aligned_malloc` и **_aligned_malloc_dbg** выделить блок памяти в основной куче, но **_aligned_malloc_dbg** включает различные возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, и *filename*/*linenumber* сведения для определения источника запросов на выделение.

**_aligned_malloc_dbg** выделяет блок памяти, добавив немного больше пространства, чем запрошено *размер*. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.

**_aligned_malloc_dbg** задает `errno` для `ENOMEM` случае сбоя выделения памяти, или если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает `_HEAP_MAXREQ`. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того **_aligned_malloc_dbg** проверяет свои параметры. Если *выравнивание* не является степенью числа 2 или *размер* равен нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает значение NULL и задает `errno` для `EINVAL`.

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_malloc_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)