---
title: _RTC_GetErrDesc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a176aa258f805a516bf36c982ba63e531a74478
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="rtcgeterrdesc"></a>_RTC_GetErrDesc

Возвращает краткое описание типа проверки на ошибки во время выполнения (RTC).

## <a name="syntax"></a>Синтаксис

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>Параметры

*errnum*<br/>
Число от нуля до единицы и меньше значения, возвращаемого **_RTC_NumErrors**.

## <a name="return-value"></a>Возвращаемое значение

Строка символов, которая содержит краткое описание одного из типов ошибок, обнаруженного системой проверки на ошибки во время выполнения. Если ошибка меньше нуля или больше или равно значению, возвращенных [_RTC_NumErrors](rtc-numerrors.md), **_RTC_GetErrDesc** возвращает значение NULL.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

Дополнительные сведения см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[Проверка ошибок во время выполнения](../../c-runtime-library/run-time-error-checking.md)<br/>
