---
title: _RTC_NumErrors | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_NumErrors
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
apitype: DLLExport
f1_keywords:
- _RTC_NumErrors
- RTC_NumErrors
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_NumErrors function
- RTC_NumErrors function
ms.assetid: 7e82adae-38e2-4f8b-bc0b-37bda8109fd1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af223e1e2d183f5357cf1d1bac96aabb042a99da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405917"
---
# <a name="rtcnumerrors"></a>_RTC_NumErrors

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
