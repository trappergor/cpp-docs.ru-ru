---
title: _realloc_dbg | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dffe9ab2f63e39953749586341e1977126ca70d8
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="reallocdbg"></a>_realloc_dbg

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

*Устойчивость данных пользователя*<br/>
Указатель на ранее выделенный блок памяти.

*newSize*<br/>
Запрошенный размер повторно выделенного блока (в байтах).

*blockType*<br/>
Запрашиваемый тип для повторно выделенного блока: **_CLIENT_BLOCK** или **_NORMAL_BLOCK**.

*filename*<br/>
Указатель на имя исходного файла, который запросил **realloc** операцию, или NULL.

*linenumber*<br/>
Номер строки в исходном файле где **realloc** операция была запрошенные или значение NULL.

*Filename* и *linenumber* доступны, только если **_realloc_dbg** была явно вызвана или [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) определена константа препроцессора.

## <a name="return-value"></a>Возвращаемое значение

При успешном выполнении эта функция возвращает указатель на пользовательскую часть перераспределенного блока памяти, вызывает новую функцию обработчика или возвращает значение NULL. Полное описание поведения возвращения см. в следующем разделе "Примечания". Дополнительные сведения о том, как используется новая функция обработчика, см. в описании функции [realloc](realloc.md).

## <a name="remarks"></a>Примечания

**_realloc_dbg** является отладочной версией [realloc](realloc.md) функции. Когда [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_realloc_dbg** сокращается до вызова **realloc**. Оба **realloc** и **_realloc_dbg** выполняют перераспределение блока памяти в основной куче, но **_realloc_dbg** включает различные функции отладки: буферы на обеих сторонах пользовательской части блока для тестирования утечек, параметр типа блока для отслеживания конкретных типов выделения, и *filename*/*linenumber* сведения для определения источника запросов на выделение.

**_realloc_dbg** перераспределяет указанный блок памяти немного больше места, чем запрошено *newSize*. *newSize* может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти. Если блок памяти перемещен, содержимое исходного блока перезаписывается.

**_realloc_dbg** задает **errno** для **ENOMEM** случае сбоя выделения памяти или если необходимый объем памяти (включая ранее упомянутую нагрузку) превышает **_HEAP_ MAXREQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

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
