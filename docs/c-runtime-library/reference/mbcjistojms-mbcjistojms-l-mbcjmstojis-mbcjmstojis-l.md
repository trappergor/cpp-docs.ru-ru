---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs:
- C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07d34331e38362a6491e3231566443b5fe03260e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l

Преобразуют символы стандартов Japan Industry Standard (JIS) и Japan Microsoft (JMS) в разных направлениях.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _mbcjistojms(
   unsigned int c
);
unsigned int _mbcjistojms_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbcjmstojis(
   unsigned int c
);
unsigned int _mbcjmstojis_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*c*<br/>
Символ для преобразования.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Для японского языкового стандарта эти функции возвращают преобразованный символ или 0, если преобразование невозможно. Для других языковых стандартов эти функции возвращают переданный символ.

## <a name="remarks"></a>Примечания

**_Mbcjistojms** функция преобразует символ Японии стандартных отраслевых (JIS) символов кандзи Microsoft (Shift-JIS). Символ преобразуется, только если руководитель и младший байт находятся в диапазоне 0x21 - 0x7E. Если руководитель или пробной байтов за пределами этого диапазона **errno** равно **EILSEQ**. Дополнительные сведения об этих и других кодах ошибок см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**_Mbcjmstojis** функция преобразует символов Shift JIS символов JIS. Символ преобразуется только в том случае, если старший байт в диапазон 0x81-0x9F и от 0xE0 - 0xFC и младший байт в диапазоне 0x40-0x7E и 0x80 - 0xFC. Обратите внимание, что некоторым кодовым точкам в этом диапазоне не соответствуют символы, в результате чего их преобразование невозможно.

Значение *c* должен быть 16-разрядное значение, старшие 8 бит представляют старший байт символа для преобразования, а которого младшие 8 битов — младший байт.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В более ранних версиях **_mbcjistojms** и **_mbcjmstojis** были вызваны **jistojms** и **jmstojis**соответственно. **_mbcjistojms**, **_mbcjistojms_l**, **_mbcjmstojis** и **_mbcjmstojis_l** следует использовать.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbcjistojms**|\<mbstring.h>|
|**_mbcjistojms_l**|\<mbstring.h>|
|**_mbcjmstojis**|\<mbstring.h>|
|**_mbcjmstojis_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Подпрограммы _ismbb](../../c-runtime-library/ismbb-routines.md)<br/>
