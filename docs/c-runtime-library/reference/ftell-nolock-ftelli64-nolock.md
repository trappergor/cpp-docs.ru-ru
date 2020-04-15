---
title: _ftell_nolock, _ftelli64_nolock
ms.date: 4/2/2020
api_name:
- _ftelli64_nolock
- _ftell_nolock
- _o__ftell_nolock
- _o__ftelli64_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftelli64_nolock
- ftelli64_nolock
- ftell_nolock
- _ftell_nolock
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
ms.openlocfilehash: fc6534daaeb3818e28e3c48dbc6d1d9586b6429e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345596"
---
# <a name="_ftell_nolock-_ftelli64_nolock"></a>_ftell_nolock, _ftelli64_nolock

Получает текущее положение указателя файла, не блокируя поток.

## <a name="syntax"></a>Синтаксис

```C
long _ftell_nolock(
   FILE *stream
);
__int64 _ftelli64_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Параметры

*Поток*<br/>
Целевой **FILE** file структуры.

## <a name="return-value"></a>Возвращаемое значение

То же самое, что **ftell** и **_ftelli64**. Для получения дополнительной информации, с [_ftelli64м.](ftell-ftelli64.md)

## <a name="remarks"></a>Remarks

Эти функции являются неблокирующих версий **ftell** и **_ftelli64**соответственно. Они идентичны **ftell** и **_ftelli64** за исключением того, что они не защищены от помех другими потоками. Они могут выполняться быстрее, так как не создают дополнительную нагрузку, связанную с блокировкой работы других потоков. Используйте эти функции только в потокобезопасных контекстах, например в однопоточных приложениях или если вызываемая область уже обрабатывает изоляцию потоков.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|Необязательный заголовок|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio.h>|\<errno.h>|
|**_ftelli64_nolock**|\<stdio.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
