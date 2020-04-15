---
title: _aligned_offset_realloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_realloc
- _o__aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: b27f5000a48ec3aafe37c6bd59e9b9acddd5bec5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350575"
---
# <a name="_aligned_offset_realloc"></a>_aligned_offset_realloc

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

*Размер*<br/>
Размер выделения памяти.

*выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*Смещение*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

**_aligned_offset_realloc** возвращает недействительный указатель на перераспределенный (и, возможно, перемещенный) блок памяти. Значение возврата **NULL** null, если размер равен нулю, и аргумент буфера не **является NULL,** или если нет достаточной доступной памяти, чтобы расширить блок до данного размера. В первом случае исходный блок освобождается. Во втором случае исходный блок не изменяется. Возвращаемое значение указывает на пространство хранилища, которое гарантированно будет соответственно выровнено для хранения объектов любого типа. Чтобы получить указатель на тип, отличающийся от void, используйте приведение типа для возвращаемого значения.

**_aligned_offset_realloc** помечения `__declspec(noalias)` и, `__declspec(restrict)`что означает, что функция гарантированно не изменять глобальные переменные и что указатель вернулся не псевдоним. Дополнительные сведения см. в разделах [noalias](../../cpp/noalias.md) и [restrict](../../cpp/restrict.md).

## <a name="remarks"></a>Remarks

Как [и _aligned_offset_malloc,](aligned-offset-malloc.md) **_aligned_offset_realloc** позволяет выровнять структуру в смещении внутри структуры.

**_aligned_offset_realloc** основанна на **malloc**. Для получения дополнительной информации об использовании **_aligned_offset_malloc,** см [Malloc](malloc.md). Если *memblock* **null,** функция вызывает **_aligned_offset_malloc** внутренне.

Эта функция устанавливает **errno** к **ENOMEM,** если распределение памяти не удалось или если запрашиваемый размер был **больше,** чем _HEAP_MAXREQ . Для получения дополнительной информации о **errno**, см [Errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Кроме того, **_aligned_offset_realloc** проверяет свои параметры. Если *выравнивание* не является силой 2 или если *смещение* больше или равно *размеру* и ненулевой, эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция возвращает **NULL** и устанавливает **errno** **в EINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>Пример

Дополнительные сведения см. в разделе [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>См. также раздел

[Выравнивание данных](../../c-runtime-library/data-alignment.md)<br/>
