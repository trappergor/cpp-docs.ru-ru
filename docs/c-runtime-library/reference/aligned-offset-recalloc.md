---
title: _aligned_offset_recalloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_recalloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- aligned_offset_recalloc
- _aligned_offset_recalloc
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
ms.openlocfilehash: 5ee163d257665b5481d6ab1ead54698ace1ef210
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561997"
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc

Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md), и инициализирует память нулями.

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_offset_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель текущего блока памяти.

*номер*<br/>
Число элементов.

*size*<br/>
Длина каждого элемента в байтах.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_offset_recalloc** возвращает указатель void на блок памяти перераспределенном (и, возможно, перемещенном). Возвращает значение **NULL** Если размер равен нулю и аргумент буфера не **NULL**, или если не хватает доступной памяти для увеличения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

**_aligned_offset_recalloc** помечен `__declspec(noalias)` и `__declspec(restrict)`, это означает, что функция гарантированно не изменит глобальные переменные и для возвращаемого указателя не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Примечания

Как и [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_recalloc** позволяет структуры выравниваться со смещением в структуре.

**_aligned_offset_recalloc** основан на **malloc**. Дополнительные сведения об использовании **_aligned_offset_malloc**, см. в разделе [malloc](malloc.md). Если *memblock* — **NULL**, эта функция вызывает **_aligned_offset_malloc** внутренним образом.

Эта функция задает **errno** для **ENOMEM** случае сбоя выделения памяти, или если запрошенный размер (*номер* * *размер* ) был больше **_HEAP_MAXREQ**. Дополнительные сведения о **errno**, см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того **_aligned_offset_recalloc** проверяет свои параметры. Если *выравнивание* не является степенью числа 2 или, если *смещение* больше или равно запрошенному размеру и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в разделе [параметр Проверка](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **NULL** и задает **errno** для **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc.h>|

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
