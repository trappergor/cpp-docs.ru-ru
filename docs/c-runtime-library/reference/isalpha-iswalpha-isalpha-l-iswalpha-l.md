---
title: isalpha, iswalpha, _isalpha_l, _iswalpha_l
ms.date: 4/2/2020
api_name:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
- _o_isalpha
- _o_iswalpha
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
- _istalpha
- _ismbcalpha_l
- isalpha
- _isalpha_l
- iswalpha
- _istalpha_l
- _iswalpha_l
helpviewer_keywords:
- _iswalpha_l function
- _isalpha_l function
- _ismbcalpha_l function
- _istalpha_l function
- _ismbcalpha function
- isalpha function
- iswalpha function
- istalpha function
- _istalpha function
ms.assetid: ed6cc2be-c4b0-4475-87ac-bc06d8c23064
ms.openlocfilehash: 187031adc0b22aff2c5418cd7e0f3e64075f1745
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343928"
---
# <a name="isalpha-iswalpha-_isalpha_l-_iswalpha_l"></a>isalpha, iswalpha, _isalpha_l, _iswalpha_l

Определяет, представляет ли целое число алфавитный символ.

## <a name="syntax"></a>Синтаксис

```C
int isalpha(
   int c
);
int iswalpha(
   wint_t c
);
int _isalpha_l(
   int c,
   _locale_t locale
);
int _iswalpha_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемое целое число.

*Языкового стандарта*<br/>
Языковой стандарт, используемый вместо текущего.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращается ненулевой, если *c* является определенным представлением алфавитного характера. **isalpha** возвращает ненулевое значение, если *c* находится в пределах диапазонов A - или a - z. **iswalpha** возвращает ненулевое значение только для широких символов, для которых [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) или **iswlower** является ненулевым; то есть, для любого широкого символа, который является одним из реализации определены набор, для которого ни один из **iswcntrl**, **iswdigit**, **iswpunct**, или **iswspace** является ненулевым. Каждая из этих процедур возвращает 0, если *c* не удовлетворяет условию теста.

В версиях этих функций, которые имеют **_l** суффикс, используется параметр локализации, который передается вместо текущего локаль. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isalpha** и **_isalpha_l** не определено, если *c* не EOF или в диапазоне от 0 до 0xFF, включительно. При использовании библиотеки CRT отладки и *c* не является одним из этих значений, функции повышают утверждение.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isalpha**|\<ctype.h>|
|**iswalpha**|\<ctype.h> или \<wchar.h>|
|**_isalpha_l**|\<ctype.h>|
|**_iswalpha_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
