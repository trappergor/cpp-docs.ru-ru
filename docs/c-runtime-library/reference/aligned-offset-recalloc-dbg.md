---
title: _aligned_offset_recalloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
ms.openlocfilehash: e363a1cb104db9973f5f9e9c67a5d40693d405ee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939750"
---
# <a name="_aligned_offset_recalloc_dbg"></a>_aligned_offset_recalloc_dbg

Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md), и инициализирует память нулями (только отладочная версия).

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_offset_recalloc_dbg(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель текущего блока памяти.

*Нумерация*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

*filename*<br/>
Указатель на имя исходного файла, который запросил операцию перераспределения или **значение NULL**.

*linenumber*<br/>
Номер строки в исходном файле, в которой была запрошена операция перераспределения, или **значение NULL**.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_offset_recalloc_dbg** возвращает указатель void на перераспределенный (и, возможно, перемещенный) блок памяти. Возвращаемое значение равно **null** , если размер равен нулю, а аргумент буфера не равен **null**, или если недостаточно памяти для расширения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

## <a name="remarks"></a>Примечания

**_aligned_offset_realloc_dbg** — это отладочная версия функции [_aligned_offset_recalloc](aligned-offset-recalloc.md) . Если [_DEBUG](../../c-runtime-library/debug.md) не определен, каждый вызов **_aligned_offset_recalloc_dbg** уменьшается до вызова **_aligned_offset_recalloc**. И **_aligned_offset_recalloc** , и **_aligned_offset_recalloc_dbg** перераспределяют блок памяти в базовой куче, но **_aligned_offset_recalloc_dbg** поддерживает несколько функций отладки: буферы с обеих сторон пользовательской части блока для проверки на наличие утечек и сведения *filename*/*LineNumber* для определения источника запросов на выделение. Отслеживание конкретных типов выделения с помощью параметра типа блока не является поддерживаемой функцией отладки для согласованных выделений. Согласованные выделения будут отображаться как тип блока _NORMAL_BLOCK.

**_aligned_offset_realloc_dbg** перераспределяет указанный блок памяти с немного больше пространства, чем запрошенный *newSize*. *newSize* может быть больше или меньше размера первоначально выделенного блока памяти. Дополнительное пространство используется диспетчером кучи отладки, чтобы связать блоки памяти отладки и предоставить приложению сведения о заголовке отладки и буферы перезаписи. Перераспределение может привести к перемещению исходного блока памяти в другое расположение в куче, а также к изменению размера блока памяти. Если блок памяти перемещен, содержимое исходного блока перезаписывается.

Эта **функция устанавливает значение** **еномем** , если выделение памяти завершилось ошибкой, или если запрошенный размер (*Размер* *номера* * ) больше **_HEAP_MAXREQ**. Дополнительные сведения о параметре " [право_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)" см **. в разделе**"переданные", "_sys_errlist" и "_sys_nerr". Кроме того, **_aligned_offset_recalloc_dbg** проверяет свои параметры. Если параметр *alignment* не является степенью 2 или *смещение* больше или равно запрошенному размеру и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **значение NULL** **и устанавливает для** **еинвал**.

Сведения о выделении, инициализации и управлении блоками памяти в отладочной версии базовой кучи, см. в статье [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Сведения о типах блоков выделения и способах их использования см. в разделе [Типы блоков в отладочной куче](/visualstudio/debugger/crt-debug-heap-details). Сведения о различиях между вызовом стандартной функции кучи и ее отладочной версии в сборке отладки приложения см. в разделе [Версии отладки функций выделения кучи](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h>|

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
