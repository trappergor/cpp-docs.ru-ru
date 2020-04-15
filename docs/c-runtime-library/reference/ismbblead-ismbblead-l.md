---
title: _ismbblead, _ismbblead_l
description: Описывает _ismbblead и _ismbblead_l функции библиотеки Runtime (CRT) корпорации Майкрософт.
ms.date: 4/2/2020
api_name:
- _ismbblead_l
- _ismbblead
- _o__ismbblead
- _o__ismbblead_l
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
- ismbblead_l
- istlead
- _ismbblead
- _ismbblead_l
- ismbblead
- _istlead
helpviewer_keywords:
- _ismbblead_l function
- ismbblead function
- _ismbblead function
- istlead function
- ismbblead_l function
- _istlead function
ms.assetid: 2abc6f75-ed5c-472e-bfd0-e905a1835ccf
ms.openlocfilehash: ee3085d49a27f2f3c97c6578463cf3a0598b73c7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343580"
---
# <a name="_ismbblead-_ismbblead_l"></a>_ismbblead, _ismbblead_l

Тестирует символ, чтобы определить, является ли это свинцово-байтное многобайтного персонажа.

## <a name="syntax"></a>Синтаксис

```C
int _ismbblead(
   unsigned int c
);
int _ismbblead_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*\
Целое число, которое требуется проверить.

*Языкового стандарта*\
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает ненулевое значение, если цель *c* является первым байтом мультибайтного символа.

## <a name="remarks"></a>Remarks

Многобайтовые символы состоят из старшего байта, за которым следует конечный байт. Старшие байты относятся к определенному диапазону данной кодировки. Например, только на странице кода 932, свинцовые байты варьируются от 0x81 - 0x9F и 0xE0 - 0xFC.

**_ismbblead** использует текущий локал для поведения, зависящем от локального. **_ismbblead_l** идентична, за исключением того, что он использует локал, передаваемый в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Когда местность UTF-8, **_ismbblead** и **_ismbblead_l** всегда возвращают сярют 0 (ложный), является ли *c* свинца байт или нет.

**_ismbblead** и **_ismbblead_l** специфичны для Майкрософт, а не являются частью библиотеки Standard C. Мы не рекомендуем вам использовать их там, где вам нужен портативный код. Для совместимости Standard C используйте **mbrlen** вместо этого.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Общие текстовые рутинные отображения

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istlead**|Всегда возвращает значение false|**_ismbblead**|Всегда возвращает значение false|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_ismbblead**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbblead_l**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Для констант манифестов, используемых в условиях проверки.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байта](../../c-runtime-library/byte-classification.md)\
[_ismbb процедуры](../../c-runtime-library/ismbb-routines.md)\
[mbrlen](mbrlen.md)
