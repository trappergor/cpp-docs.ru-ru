---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 96fe9e7fda0d0cdfdbfa5462e4f601e3649e2233
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348878"
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

Размещение памяти на указанной границе выравнивания (только в отладочной версии).

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Размер запрошенного выделения памяти.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения или **NULL**.

*linenumber*<br/>
Номер строки в файле источника, в которой была запрошена операция выделения или **NULL**.

## <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, которая была выделена или **NULL** Если произошел сбой операции.

## <a name="remarks"></a>Примечания

**_aligned_offset_malloc_dbg** является отладочной версией [_aligned_offset_malloc](aligned-offset-malloc.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_aligned_offset_malloc_dbg** сокращается до вызова **_aligned_offset_malloc**. Оба **_aligned_offset_malloc** и **_aligned_offset_malloc_dbg** выделить блок памяти в основной куче, но **_aligned_offset_malloc_dbg** предлагает несколько вариантов возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, и *filename*/*linenumber* сведения для определения источника запросов на выделение. Отслеживание конкретных типов выделения с параметр типа блока не является компонентом поддерживаемых отладки для выровненные распределения. Выровненные распределения будут отображаться как _NORMAL_BLOCK тип блока.

**_aligned_offset_malloc_dbg** выделяет блок памяти, добавив немного больше пространства, чем запрошено *размер*. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.

**_aligned_offset_malloc_dbg** полезна в случаях, когда необходимо выравнивание вложенного элемента; например, если требуется выравнивание вложенного класса.

**_aligned_offset_malloc_dbg** основан на **malloc**; Дополнительные сведения см. в разделе [malloc](malloc.md).

Эта функция задает **errno** для **ENOMEM** случае сбоя выделения памяти, или если запрошенный размер был больше, чем **_HEAP_MAXREQ**. Дополнительные сведения о **errno**, см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того **_aligned_offset_malloc** проверяет свои параметры. Если *выравнивание* не является степенью числа 2 или, если *смещение* больше или равно *размер* и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **NULL** и задает **errno** для **EINVAL**.

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

Дополнительные сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
