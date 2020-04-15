---
title: _mbbtype, _mbbtype_l
ms.date: 4/2/2020
api_name:
- _mbbtype
- _mbbtype_l
- _o__mbbtype
- _o__mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
ms.openlocfilehash: 7e2e818ed70ec393e4f81008f76ca9efe9cfa7e7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341400"
---
# <a name="_mbbtype-_mbbtype_l"></a>_mbbtype, _mbbtype_l

Возвращает тип байта, основываясь на предыдущем байте.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbbtype(
   unsigned char c,
   int type
);
int _mbbtype_l(
   unsigned char c,
   int type,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемый символ.

*тип*<br/>
Тип байта для проверки.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbbtype** возвращает тип байта в строке. Это решение является контекст-чувствительным, как указано в значении *типа*, который обеспечивает условие контрольного теста. *тип* — это тип предыдущего байта в строке. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Значение *типа*|**_mbbtype** тесты для|Возвращаемое значение|*C*|
|---------------------|--------------------------|------------------|---------|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_SINGLE** (0)|Одноместный байт (0x20 - 0x7E, 0xA1 - 0xDF)|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_LEAD** (1)|Свинец мультибайтного персонажа (0x81 - 0x9F, 0xE0 - 0xFC)|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_ILLEGAL**<br /><br /> ( -1)|Недействительный символ (любое значение, кроме 0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|
|1|Допустимый младший байт|**_MBC_TRAIL** (2)|Трейлинг байт мультибайтного персонажа (0x40 - 0x7E, 0x80 - 0xFC)|
|1|Допустимый младший байт|**_MBC_ILLEGAL**<br /><br /> ( -1)|Недействительный символ (любое значение, кроме 0x20 - 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|

## <a name="remarks"></a>Remarks

Функция **_mbbtype** определяет тип байта в мультибайтном символе. Если значение *типа* является каким-либо значением, за исключением 1, **_mbbtype** тестов для действительного однобайного или свинцового байта мультибайтного символа. Если значение *типа* 1, **_mbbtype** тестов для действительного следа байт многобайтного символа.

На значение вывода влияет настройка **LC_CTYPE** категории локализуем; см [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. В **_mbbtype** версии этой функции используется текущий локаль для этого поведения, зависящем от локального; **_mbbtype_l** версия идентична, за исключением того, что она использует параметр локализации, который передается в вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В более ранних версиях **_mbbtype** был назван **chkctype**. Для нового кода используйте вместо этого **_mbbtype.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для определения констант манифеста, которые используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
