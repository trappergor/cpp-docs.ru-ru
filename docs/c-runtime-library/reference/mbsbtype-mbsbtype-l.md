---
title: _mbsbtype, _mbsbtype_l
ms.date: 4/2/2020
api_name:
- _mbsbtype_l
- _mbsbtype
- _o__mbsbtype
- _o__mbsbtype_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: d71a061d9af5028c9bc6b4008f9904606a233592
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340874"
---
# <a name="_mbsbtype-_mbsbtype_l"></a>_mbsbtype, _mbsbtype_l

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

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbsbtype** и **_mbsbtype_l** возвращает величину с указанием результата теста на указанном байте. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Возвращаемое значение|Тип байта|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Однобайтовый символ. Например, на странице кода **932, _mbsbtype** возвращает 0, если указанный байт находится в пределах 0x20 - 0x7E или 0xA1 - 0xDF.|
|**_MBC_LEAD** (1)|Старший байт многобайтового символа. Например, на странице кода 932 **_mbsbtype** возвращает 1, если указанный байт находится в пределах 0x81 - 0x9F или 0xE0 - 0xFC.|
|**_MBC_TRAIL** (2)|Младший байт многобайтового символа. Например, на странице кода 932 **_mbsbtype** возвращает 2, если указанный байт находится в пределах 0x40 - 0x7E или 0x80 - 0xFC.|
|**_MBC_ILLEGAL** (-1)|**NULL** строка, недействительный характер, или нулевой байт найден до байт на смещение *кол* в *mbstr*.|

## <a name="remarks"></a>Remarks

Функция **_mbsbtype** определяет тип байта в многобайтной строке символов. Функция рассматривает только байт при смещении *в* *mbstr,* игнорируя недействительные символы перед указанным байтом.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версия этой функции без **_l** суффикса использует текущий локали для этого поведения, зависящем от локали; версия с **_l** суффикса идентична, за исключением того, что она использует параметр локализации, передаваемый вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если строка ввода **NULL,** вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается **eINVAL** и функция **возвращается _MBC_ILLEGAL**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для констант манифеста используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
