---
title: _get_doserrno
ms.date: 4/2/2020
api_name:
- _get_doserrno
- _o__get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 2d5d4e224b39e9fa597e12975d27fa5720fbfbc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345258"
---
# <a name="_get_doserrno"></a>_get_doserrno

Возвращает значение ошибки операционной системой до его перевода в значение **errno.**

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на множество, чтобы быть заполнены с текущей стоимости **_doserrno** глобального макроса.

## <a name="return-value"></a>Возвращаемое значение

Если **_get_doserrno** удастся, он возвращается ноль; если это не удается, он возвращает код ошибки. Если *pValue* является **NULL,** вызовуется обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** к **EINVAL** и возвращает **EINVAL**.

## <a name="remarks"></a>Remarks

**Глобальный _doserrno** макрос установлен на нулевой отметку во время инициализации CRT, до начала выполнения процесса. Ему присваивается значение ошибки операционной системы, возвращаемое вызовом любой функции уровня системы. Вызов возвращает ошибку операционной системы и никогда не сбрасывается до нуля во время выполнения. При написании кода для проверки значения ошибки, возвращенного функцией, всегда четко **_doserrno,** используя [_set_doserrno](set-doserrno.md) перед вызовом функции. Поскольку другой вызов функции может перезаписать **_doserrno,** проверьте значение, используя **_get_doserrno** сразу после вызова функции.

Мы рекомендуем [_get_errno](get-errno.md) вместо **_get_doserrno** для портативных кодов ошибок.

Возможные значения **_doserrno** определяются в \<> errno.h.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

**_get_doserrno** — это расширение корпорации Майкрософт. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
