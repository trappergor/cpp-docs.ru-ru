---
title: _get_doserrno
ms.date: 11/04/2016
apiname:
- _get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 700f710e6d94f48b03697325bb720dbc539fe04e
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331026"
---
# <a name="getdoserrno"></a>_get_doserrno

Возвращает значение ошибки, возвращенный операционной системы, прежде чем он будет преобразован в **errno** значение.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на целое число, чтобы быть подставлено текущее значение **_doserrno** глобального макроса.

## <a name="return-value"></a>Возвращаемое значение

Если **_get_doserrno** завершается успешно, он возвращает ноль; Если не удается, он возвращает код ошибки. Если *pValue* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

## <a name="remarks"></a>Примечания

**_Doserrno** глобального макроса равно нулю во время инициализации CRT, до начала выполнения обработки. Ему присваивается значение ошибки операционной системы, возвращаемое вызовом любой функции уровня системы. Вызов возвращает ошибку операционной системы и никогда не сбрасывается до нуля во время выполнения. При написании кода для проверки значения ошибки, возвращаемого функцией, всегда выполняйте Сброс **_doserrno** с помощью [_set_doserrno](set-doserrno.md) до вызова функции. Поскольку другой вызов функции может перезаписать **_doserrno**, проверьте значение с помощью **_get_doserrno** сразу же после вызова функции.

Мы рекомендуем [_get_errno](get-errno.md) вместо **_get_doserrno** для переносимых кодов ошибок.

Возможные значения **_doserrno** определяются в \<errno.h >.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

**_get_doserrno** является расширением Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
