---
title: _get_doserrno | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7cef2c068fad2f18cb1d11d33e551588800cb64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399573"
---
# <a name="getdoserrno"></a>_get_doserrno

Возвращает значение ошибки, возвращаемый операционной системой, прежде чем он будет преобразован в **errno** значение.

## <a name="syntax"></a>Синтаксис

```C
errno_t _get_doserrno( 
   int * pValue 
);
```

### <a name="parameters"></a>Параметры

*pValue*<br/>
Указатель на целое число будет заполнена текущим значением **_doserrno** глобального макроса.

## <a name="return-value"></a>Возвращаемое значение

Если **_get_doserrno** завершается успешно, он возвращает значение 0, если не удается, он возвращает код ошибки. Если *pValue* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **EINVAL**.

## <a name="remarks"></a>Примечания

**_Doserrno** глобального макроса задается равным нулю во время инициализации CRT, до начала выполнения обработки. Ему присваивается значение ошибки операционной системы, возвращаемое вызовом любой функции уровня системы. Вызов возвращает ошибку операционной системы и никогда не сбрасывается до нуля во время выполнения. При написании кода, чтобы проверить значение ошибки, возвращаемые функцией, всегда снимите **_doserrno** с помощью [_set_doserrno](set-doserrno.md) до вызова функции. Поскольку другой вызов функции может перезаписать **_doserrno**, проверьте значение с помощью **_get_doserrno** сразу после вызова функции.

Мы рекомендуем [_get_errno](get-errno.md) вместо **_get_doserrno** коды переносимой ошибок.

Возможные значения **_doserrno** определены в \<errno.h >.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

**_get_doserrno** является расширением Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
