---
title: _mbsbtype, _mbsbtype_l
ms.date: 11/04/2016
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
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: 5c2927b4e4b68b1284341fe7e767ec50feb21a44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566807"
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

**_mbsbtype** и **_mbsbtype_l** возвращает целое число, указывающее результат проверки указанного байта. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Возвращаемое значение|Тип байта|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Однобайтовый символ. Например, в кодовой странице 932 функция **_mbsbtype** возвращает 0, если указанный байт находится в диапазоне 0x20 – 0x7E или 0xA1 – 0xDF.|
|**_MBC_LEAD** (1)|Старший байт многобайтового символа. Например, в кодовой странице 932 функция **_mbsbtype** возвращает 1, если указанный байт находится в диапазоне 0x81 – 0x9F или 0xE0 – 0xFC.|
|**_MBC_TRAIL** (2)|Младший байт многобайтового символа. Например, в кодовой странице 932 функция **_mbsbtype** возвращает 2, если указанный байт находится в диапазоне 0x40 – 0x7E или 0x80 – 0xFC.|
|**_MBC_ILLEGAL** (-1)|**NULL** строку, недопустимый символ или байт null перед байтом со смещением *число* в *mbstr*.|

## <a name="remarks"></a>Примечания

**_Mbsbtype** функция определяет тип байта в строке многобайтовых символов. Функция проверяет только байт со смещением *число* в *mbstr*, пропуская недопустимые символы перед указанным байтом.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версия этой функции без **_l** суффикс использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; версии с **_l** суффиксом идентичны, но использует переданный параметр языкового стандарта в вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если входная строка равна **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает **_MBC_ILLEGAL**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для констант манифеста используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
