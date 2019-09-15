---
title: _RTC_NumErrors
ms.date: 11/04/2016
api_name:
- _RTC_NumErrors
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
- _RTC_NumErrors
- RTC_NumErrors
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
ms.openlocfilehash: 72056208ca6d714f788ae325b90786f5be4ab443
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949036"
---
# <a name="_rtc_numerrors"></a>_RTC_NumErrors

Возвращает общее количество ошибок, которое может быть обнаружено путем проверки на ошибки во время выполнения (RTC). Вы можете использовать это число в качестве элемента управления в цикле **for**, где каждое значение в цикле передается в [_RTC_GetErrDesc](rtc-geterrdesc.md).

## <a name="syntax"></a>Синтаксис

```C

int _RTC_NumErrors( void );
```

## <a name="return-value"></a>Возвращаемое значение

Целое число, представляющее общее количество ошибок, которое может быть обнаружено проверками на ошибки во время выполнения Visual C++.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_RTC_NumErrors**|\<rtcapi.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[_RTC_GetErrDesc](rtc-geterrdesc.md)<br/>
[Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)<br/>
