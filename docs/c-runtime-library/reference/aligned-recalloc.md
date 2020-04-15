---
title: _aligned_recalloc
ms.date: 4/2/2020
api_name:
- _aligned_recalloc
- _o__aligned_recalloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- aligned_recalloc
- _aligned_recalloc
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
ms.openlocfilehash: af12322742c777cda879e01cb9c054297f807725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350497"
---
# <a name="_aligned_recalloc"></a>_aligned_recalloc

Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](aligned-malloc.md) или [_aligned_offset_malloc](aligned-offset-malloc.md), и инициализирует память нулями.

## <a name="syntax"></a>Синтаксис

```C
void * _aligned_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель текущего блока памяти.

*число*<br/>
Число элементов.

*Размер*<br/>
Размер каждого элемента в байтах.

*выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_recalloc** возвращает недействительный указатель на перераспределенный (и, возможно, перемещенный) блок памяти. Значение возврата **NULL** null, если размер равен нулю, и аргумент буфера не **является NULL,** или если нет достаточной доступной памяти, чтобы расширить блок до данного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

Будет ошибкой повторно выделить память и изменить выравнивание блока.

## <a name="remarks"></a>Remarks

**_aligned_recalloc** основанна на **malloc**. Для получения дополнительной информации об использовании **_aligned_offset_malloc,** см [Malloc](malloc.md).

Эта функция устанавливает **errno** к **ENOMEM,** если распределение памяти не удалось или если запрашиваемый размер был **больше,** чем _HEAP_MAXREQ . Для получения дополнительной информации о **errno**, см [Errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, **_aligned_recalloc** проверяет свои параметры. Если *выравнивание* не является силой 2, эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция возвращает **NULL** и устанавливает **errno** **в EINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc.h>|

## <a name="see-also"></a>См. также раздел

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
