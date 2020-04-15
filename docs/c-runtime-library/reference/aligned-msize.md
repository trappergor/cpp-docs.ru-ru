---
title: _aligned_msize
ms.date: 4/2/2020
api_name:
- _aligned_msize
- _o__aligned_msize
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
- _aligned_msize
- aligned_msize
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
ms.openlocfilehash: 21ae07c90bbf9a729a212a97b7de3e0916f8e2c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350601"
---
# <a name="_aligned_msize"></a>_aligned_msize

Возвращает размер блока памяти, выделенного в куче.

## <a name="syntax"></a>Синтаксис

```C
size_t _msize(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Параметры

*memblock*<br/>
Указатель на блок памяти.

*выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*Смещение*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

Возвращает размер (в байтах) как целое число без знака.

## <a name="remarks"></a>Remarks

Функция **_aligned_msize** возвращает размер байтов блока памяти, выделенного вызовом [_aligned_malloc](aligned-malloc.md) или [_aligned_realloc.](aligned-realloc.md) Значения *выравнивания* и *смещения* должны быть такими же, как и значения, передаваемые функции, выделенной блоком.

Когда приложение связано с отладкой версии библиотек исправления C, **_aligned_msize** решает [_aligned_msize_dbg.](aligned-msize-dbg.md) Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Эта функция проверяет свои параметры. Если *memblock* является нулевой указатель или *выравнивание* не является силой 2, **_msize** вызывает недействительный обработчик параметров, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если ошибка обработана, функция устанавливает **errno** к **EINVAL** и возвращает -1.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
