---
title: _ismbbtrail, _ismbbtrail_l
ms.date: 4/2/2020
api_name:
- _ismbbtrail
- _ismbbtrail_l
- _o__ismbbtrail
- _o__ismbbtrail_l
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
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
ms.openlocfilehash: 5e8615adf5d17986c1a52658fe5d680cc326976a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343390"
---
# <a name="_ismbbtrail-_ismbbtrail_l"></a>_ismbbtrail, _ismbbtrail_l

Определяет, является ли байт конечным байтом многобайтового символа.

## <a name="syntax"></a>Синтаксис

```C
int _ismbbtrail(
   unsigned int c
);
int _ismbbtrail_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Целое число, которое требуется проверить.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_ismbbtrail** возвращает ненулевое значение, если цель *c* является вторым байтом мультибайтного символа. Например, только для кодовой страницы 932, допустимые диапазоны: 0x40–0x7E и 0x80–0xFC.

## <a name="remarks"></a>Remarks

**_ismbbtrail** использует текущий локал для поведения, зависящем от локального. **_ismbbtrail_l** идентичен, за исключением того, что он использует локал, который прошел в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_ismbbtrail**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbbtrail_l**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Для констант манифестов, используемых в условиях проверки.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb рутины](../../c-runtime-library/ismbb-routines.md)<br/>
