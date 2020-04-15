---
title: isascii, __isascii, iswascii
ms.date: 4/2/2020
api_name:
- iswascii
- __isascii
- _o_iswascii
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswascii
- istascii
- __isascii
- _istascii
- isascii
- ctype/isascii
- ctype/__isascii
- corecrt_wctype/iswascii
helpviewer_keywords:
- __isascii function
- _isascii function
- isascii function
- _istascii function
- istascii function
- iswascii function
ms.assetid: ba4325ad-7cb3-4fb9-b096-58906d67971a
ms.openlocfilehash: aeb9c27fee4d179cc16caa50c6f0aae521402beb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343912"
---
# <a name="isascii-__isascii-iswascii"></a>isascii, __isascii, iswascii

Определяет, является ли определенный символ символом ASCII.

## <a name="syntax"></a>Синтаксис

```C
int __isascii(
   int c
);
int iswascii(
   wint_t c
);

#define isascii __isascii
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращается ненулевой, если **c** является особым представлением характера ASCII. **__isascii** возвращает ненулевое значение, если **c** является символом ASCII (в диапазоне 0x00 - 0x7F). **iswascii** возвращает ненулевое значение, если **c** является широкохарактерным представлением символа ASCII. Каждая из этих процедур возвращает 0, если **c** не удовлетворяет условию теста.

## <a name="remarks"></a>Remarks

Оба **__isascii** и **iswascii** реализованы в качестве макросов, если допроцессор макро_CTYPE_DISABLE_MACROS не определен.

Для обратной совместимости **isascii** реализуется в качестве макроса только в том случае, если [&#95;&#95;stDC&#95;&#95;](../../preprocessor/predefined-macros.md) не определенили или определены как 0; в противном случае это неопределен.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h> или \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> или \<wchar.h>|

**Isascii**, **__isascii** и **iswascii функции** Microsoft-специфических. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
