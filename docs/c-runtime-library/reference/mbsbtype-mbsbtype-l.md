---
title: _mbsbtype, _mbsbtype_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsbtype_l
- _mbsbtype
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
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54b82eae4826bd6a359f2cf0d4e74bccd32f81b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="mbsbtype-mbsbtypel"></a>_mbsbtype, _mbsbtype_l

Возвращает тип байта в строке.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*mbstr*<br/>
Адрес последовательности многобайтовых символов.

*count*<br/>
Смещение в байтах относительно заголовка строки.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbsbtype** и **_mbsbtype_l** возвращает целочисленное значение, указывающее результат теста на указанный байт. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Возвращаемое значение|Тип байта|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Однобайтовый символ. Например, в кодовой странице 932 **_mbsbtype** возвращает 0, если указанный байт — в диапазоне от 0x20 — 0x7E или 0xA1 - 0xDF.|
|**_MBC_LEAD** (1)|Старший байт многобайтового символа. Например, в кодовой странице 932 **_mbsbtype** возвращает 1, если указанного байтового входит в диапазон 0x81-0x9F и от 0xE0 - 0xFC.|
|**_MBC_TRAIL** (2)|Младший байт многобайтового символа. Например, в кодовой странице 932 **_mbsbtype** возвращает 2 в том случае, если указанного байтового диапазона 0x40-0x7E и 0x80 - 0xFC.|
|**_MBC_ILLEGAL** (-1)|**Значение NULL** string, недопустимый символ или **NULL** байтов найдено до байт по смещению *число* в *mbstr*.|

## <a name="remarks"></a>Примечания

**_Mbsbtype** функция определяет тип байта в строке многобайтовых символов. Функция проверяет только байт по смещению *число* в *mbstr*, игнорирование недопустимых символов перед указанным байтов.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версия этой функции без **_l** суффикс использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; версии с **_l** суффикс идентична, но использует переданный параметр языкового стандарта в вместо него. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если входная строка **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает **_MBC_ILLEGAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для констант манифеста используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
