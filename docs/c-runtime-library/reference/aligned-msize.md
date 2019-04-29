---
title: _aligned_msize
ms.date: 11/04/2016
apiname:
- _aligned_msize
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
- _aligned_msize
- aligned_msize
helpviewer_keywords:
- aligned_msize function
- _aligned_msize function
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
ms.openlocfilehash: 97c739eed1f54f0c6705d37542eb13c6ec6879d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341929"
---
# <a name="alignedmsize"></a>_aligned_msize

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

*Выравнивание*<br/>
Значение выравнивания, которое должно быть целой степенью числа 2.

*offset*<br/>
Смещение в выделение памяти для принудительного выполнения выравнивания.

## <a name="return-value"></a>Возвращаемое значение

Возвращает размер (в байтах) как целое число без знака.

## <a name="remarks"></a>Примечания

**_Aligned_msize** функция возвращает размер в байтах блока памяти, выделенной с помощью вызова [_aligned_malloc](aligned-malloc.md) или [_aligned_realloc](aligned-realloc.md). *Выравнивание* и *смещение* значения должны быть так же, как значения, переданные функции, выделившей блок.

Когда приложение связано с отладочной версией библиотек времени выполнения языка C, **_aligned_msize** разрешается [_aligned_msize_dbg](aligned-msize-dbg.md). Дополнительные сведения об управлении кучей в процессе отладки см. в разделе [Куча отладки CRT](/visualstudio/debugger/crt-debug-heap-details).

Эта функция проверяет свои параметры. Если *memblock* является пустым указателем или *выравнивание* не является степенью двойки, **_msize** вызывает обработчик недопустимого параметра, как описано в [проверка параметров ](../../c-runtime-library/parameter-validation.md). Если ошибка обработана, функция задает **errno** для **EINVAL** и возвращает – 1.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_msize**|\<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
