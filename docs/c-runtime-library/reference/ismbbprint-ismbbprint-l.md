---
title: _ismbbprint, _ismbbprint_l
ms.date: 4/2/2020
api_name:
- _ismbbprint_l
- _ismbbprint
- _o__ismbbprint
- _o__ismbbprint_l
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
- _ismbbprint_l
- _ismbbprint
- ismbbprint
- ismbbprint_l
helpviewer_keywords:
- ismbbprint_l function
- ismbbprint function
- _ismbbprint function
- _ismbbprint_l function
ms.assetid: d08a061c-18a8-48f2-a75d-bff4870aec9d
ms.openlocfilehash: 8da69247d090c2067b0efda3c47f92bbeb729e49
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343524"
---
# <a name="_ismbbprint-_ismbbprint_l"></a>_ismbbprint, _ismbbprint_l

Определяет, является ли указанный многобайтовой символ печатным символом.

## <a name="syntax"></a>Синтаксис

```C
int _ismbbprint(
   unsigned int c
);
int _ismbbprint_l(
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

**_ismbbprint** возвращает ненулевое значение, если выражение:

`isprint(c) || _ismbbkprint(c)`

является незерной для *c,* или 0, если это не так. **_ismbbprint** использует текущий локал для любого поведения, зависящем от локализуемого. **_ismbbprint_l** идентичен, за исключением того, что он использует локал, передаваемый в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbbprint**|\<mbctype.h>|
|**_ismbbprint_l**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb рутины](../../c-runtime-library/ismbb-routines.md)<br/>
