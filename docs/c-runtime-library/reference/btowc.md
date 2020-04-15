---
title: btowc
ms.date: 4/2/2020
api_name:
- btowc
- _o_btowc
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- btowc
helpviewer_keywords:
- btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
ms.openlocfilehash: b4262f31c95b5272e3917f58a6c945577d401f16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333762"
---
# <a name="btowc"></a>btowc

Определяет, представляет ли целое число допустимый однобайтовый символ в начальном состоянии сдвига.

## <a name="syntax"></a>Синтаксис

```C
wint_t btowc(
   int character
);
```

### <a name="parameters"></a>Параметры

*Символ*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Возвращает представление символа в виде расширенного символа, если целое число представляет допустимый однобайтовый символ в начальном состоянии сдвига. Возвращает символ WEOF, если целое число является символом EOF или не является допустимым однобайтовым символом в начальном состоянии сдвига. На выход этой функции влияет текущая **LC_TYPE.**

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**btowc**|\<stdio.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
