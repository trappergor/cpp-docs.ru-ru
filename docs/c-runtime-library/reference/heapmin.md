---
title: _heapmin
ms.date: 4/2/2020
api_name:
- _heapmin
- _o__heapmin
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
- _heapmin
- heapmin
helpviewer_keywords:
- heap memory
- minimizing heaps
- memory, releasing
- heaps, releasing unused memory
- _heapmin function
- heapmin function
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
ms.openlocfilehash: 6e8f90a7aa74ca3e890307f95b5f293f0be3575f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343997"
---
# <a name="_heapmin"></a>_heapmin

Освобождает неиспользуемую память кучи для операционной системы.

## <a name="syntax"></a>Синтаксис

```C
int _heapmin( void );
```

## <a name="return-value"></a>Возвращаемое значение

В случае успеха **_heapmin** возвращает 0; в противном случае функция возвращает -1 и устанавливает **errno** в **ENOSYS.**

Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Remarks

Функция **_heapmin** сводит к минимуму кучи, высвобождая неиспользованную память кучи в операционную систему. Если операционная система не поддерживает **_heapmin**(например, Windows 98), функция возвращает -1 и устанавливает **errno** в **ENOSYS.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_heapmin**|\<malloc.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Распределение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[Бесплатный](free.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
[malloc](malloc.md)<br/>
