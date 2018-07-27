---
title: _mbbtype, _mbbtype_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbbtype
- _mbbtype_l
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
- _mbbtype_l
- mbbtype
- mbbtype_l
- _mbbtype
dev_langs:
- C++
helpviewer_keywords:
- _mbbtype function
- _mbbtype_l function
- mbbtype function
- mbbtype_l function
ms.assetid: b8e34b40-842a-4298-aa39-0bd2d8e51c2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91b78b0dc57873810f96a793288da3f1457299de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404419"
---
# <a name="mbbtype-mbbtypel"></a>_mbbtype, _mbbtype_l

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

*c*<br/>
Проверяемый символ.

*type*<br/>
Тип байта для проверки.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbbtype** возвращает тип байта в строке. Это решение зависит от контекста, в соответствии с значение *типа*, который предоставляет условие проверки управления. *Тип* — это тип предыдущего байта в строке. Константы манифеста, представленные в приведенной ниже таблице, определены в файле Mbctype.h.

|Значение *типа*|**_mbbtype** тестов для|Возвращаемое значение|*c*|
|---------------------|--------------------------|------------------|---------|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_SINGLE** (0)|Один байт (0x20 — 0x7E, 0xA1 - 0xDF)|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_LEAD** (1)|Старший байт многобайтового символа (0x81 - 0x9F, 0xE0 - 0xFC)|
|Любое значение, кроме 1|Допустимый одиночный байт или старший байт|**_MBC_ILLEGAL**<br /><br /> ( -1)|Недопустимый символ (любое значение, кроме 0x20 — 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|
|1|Допустимый младший байт|**_MBC_TRAIL** (2)|Конечный байт многобайтового символа (0x40 - 0x7E, 0x80 - 0xFC)|
|1|Допустимый младший байт|**_MBC_ILLEGAL**<br /><br /> ( -1)|Недопустимый символ (любое значение, кроме 0x20 — 0x7E, 0xA1 - 0xDF, 0x81 - 0x9F, 0xE0 - 0xFC|

## <a name="remarks"></a>Примечания

**_Mbbtype** функция определяет тип байта в многобайтовом символе. Если значение *тип* имеет любое значение, кроме 1, **_mbbtype** проверяет допустимый одиночный байт или старший байт многобайтового символа. Если значение *тип* -1, **_mbbtype** проверяет допустимый младший байт многобайтового символа.

Выходное значение зависит от настройки **LC_CTYPE** категории языкового стандарта см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. **_Mbbtype** версия этой функции использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; **_mbbtype_l** версии идентична, но использует переданный параметр языкового стандарта . Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В более ранних версиях **_mbbtype** назывался **chkctype**. В новом коде используйте **_mbbtype** вместо него.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_mbbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Для определения констант манифеста, которые используются в качестве возвращаемых значений.

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
