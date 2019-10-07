---
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 4fbacb170fd1ae1ce92de4a11ea85ff42b3942a0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939769"
---
# <a name="_aligned_offset_malloc_dbg"></a>_aligned_offset_malloc_dbg

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
Указатель на имя исходного файла, который запросил операцию выделения, или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция выделения, или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, который был выделен, или **значение NULL** , если операция завершилась ошибкой.

## <a name="remarks"></a>Примечания

**_aligned_offset_malloc_dbg** — это отладочная версия функции [_aligned_offset_malloc](aligned-offset-malloc.md) . Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_aligned_offset_malloc_dbg** уменьшается до вызова **_aligned_offset_malloc**. **_Aligned_offset_malloc** и **_aligned_offset_malloc_dbg** выделяют блок памяти в базовой куче, но **_aligned_offset_malloc_dbg** предлагает несколько функций отладки: буферы с обеих сторон пользовательской части блока в Проверьте наличие утечек и сведения *filename*/*LineNumber* , чтобы определить происхождение запросов на выделение. Отслеживание конкретных типов выделения с помощью параметра типа блока не является поддерживаемой функцией отладки для согласованных выделений. Согласованные выделения будут отображаться как тип блока _NORMAL_BLOCK.

**_aligned_offset_malloc_dbg** выделяет блок памяти с немного больше пространства, чем запрошенный *Размер*. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. При выделении блока пользовательская часть блока заполняется значением 0xCD, а все буферы перезаписи — значением 0xFD.

**_aligned_offset_malloc_dbg** полезен в ситуациях, когда для вложенного элемента требуется выравнивание. Например, если для вложенного класса требуется выравнивание.

**_aligned_offset_malloc_dbg** основан на **malloc**; Дополнительные сведения см. в разделе [malloc](malloc.md).

Эта **функция устанавливает** **еномем** в случае сбоя выделения памяти или если запрошенный размер был больше **_HEAP_MAXREQ**. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr". Кроме того, **_aligned_offset_malloc** проверяет свои параметры. Если параметр *alignment* не является степенью 2 или *смещение* больше или равно *размеру* и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **значение NULL** **и устанавливает для** **еинвал**.

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
