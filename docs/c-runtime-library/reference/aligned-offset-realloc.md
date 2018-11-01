---
title: _aligned_offset_realloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: d5f87f9bdfff262826b8d4cc4da86069588cf9db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471322"
---
# <a name="alignedoffsetrealloc"></a>_aligned_offset_realloc

Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель текущего блока памяти.

*size*<br/>
Размер выделения памяти.

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_offset_realloc** возвращает указатель void на блок памяти перераспределенном (и, возможно, перемещенном). Возвращает значение **NULL** Если размер равен нулю и аргумент буфера не **NULL**, или если не хватает доступной памяти для увеличения блока до заданного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

**_aligned_offset_realloc** помечен `__declspec(noalias)` и `__declspec(restrict)`, это означает, что функция гарантированно не изменит глобальные переменные и для возвращаемого указателя не имеет псевдонима. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Примечания

Как и [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_realloc** позволяет структуры выравниваться со смещением в структуре.

**_aligned_offset_realloc** основан на **malloc**. Дополнительные сведения об использовании **_aligned_offset_malloc**, см. в разделе [malloc](malloc.md). Если *memblock* — **NULL**, эта функция вызывает **_aligned_offset_malloc** внутренним образом.

Эта функция задает **errno** для **ENOMEM** случае сбоя выделения памяти, или если запрошенный размер был больше, чем **_HEAP_MAXREQ**. Дополнительные сведения о **errno**, см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того **_aligned_offset_realloc** проверяет свои параметры. Если *выравнивание* не является степенью числа 2 или, если *смещение* больше или равно *размер* и не равно нулю, эта функция вызывает обработчик недопустимого параметра, как описано в [ Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция возвращает **NULL** и задает **errno** для **EINVAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
