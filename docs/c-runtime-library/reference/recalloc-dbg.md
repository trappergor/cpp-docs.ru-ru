---
title: _recalloc_dbg
ms.date: 11/04/2016
apiname:
- _recalloc_dbg
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
- recalloc_dbg
- _recalloc_dbg
helpviewer_keywords:
- _recalloc_dbg function
- recalloc_dbg function
ms.assetid: 43c3e9b2-be6d-4508-9b0f-3220c8a47ca3
ms.openlocfilehash: e2782492d3338b5b548db0153b6123fb82ff5e72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653275"
---
# <a name="recallocdbg"></a>_recalloc_dbg

Повторно выделяет массив и инициализирует его элементы нулями (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void *_recalloc_dbg(
   void *userData,
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*userData*<br/>
Указатель на ранее выделенный блок памяти.

*номер*<br/>
Запрошенное число блоков памяти.

*size*<br/>
Запрошенный размер каждого блока памяти (байт).

*blockType*<br/>
Запрошенный тип блока памяти: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details).

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию выделения или **NULL**.

*linenumber*<br/>
Номер строки в файле источника, в которой была запрошена операция выделения или **NULL**.

*Filename* и *linenumber* параметры доступны только тогда, когда **_recalloc_dbg** была явно вызвана или [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) определена константа препроцессора.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении эта функция возвращает указатель на пользовательская часть перераспределенного блока памяти, вызывает новую функцию обработчик либо возвращает **NULL**. Полное описание поведения возвращения см. в следующем разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [_recalloc](recalloc.md).

## <a name="remarks"></a>Примечания

**_recalloc_dbg** является отладочной версией [_recalloc](recalloc.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_recalloc_dbg** сокращается до вызова **_recalloc**. Оба **_recalloc** и **_recalloc_dbg** выполняют перераспределение блока памяти в основной куче, но **_recalloc_dbg** включает различные возможности отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр для отслеживания конкретных типов выделения, типа блока и *filename*/*linenumber* сведения для определения источника запросов выделения памяти.

**_recalloc_dbg** перераспределяет указанный блок памяти с немного больше пространства, чем запрошено (*номер* * *размер*) которого может быть больше или меньше, чем размер первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти. Пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.

**_recalloc_dbg** задает **errno** для **ENOMEM** при сбое выделения памяти; **EINVAL** возвращается, если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает **_HEAP_MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [Сведения о куче отладки CRT](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_recalloc_dbg**|\<crtdbg.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Только отладочные версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Процедуры отладки](../../c-runtime-library/debug-routines.md)<br/>
