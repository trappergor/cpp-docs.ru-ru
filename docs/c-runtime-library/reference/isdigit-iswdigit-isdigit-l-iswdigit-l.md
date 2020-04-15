---
title: isdigit, iswdigit, _isdigit_l, _iswdigit_l
ms.date: 4/2/2020
api_name:
- _isdigit_l
- iswdigit
- _iswdigit_l
- isdigit
- _o_isdigit
- _o_iswdigit
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _iswdigit_l
- _isdigit_l
- iswdigit
- isdigit
- _istdigit
- _istdigit_l
helpviewer_keywords:
- iswdigit function
- iswdigit_l function
- _iswdigit_l function
- _istdigit_l function
- _istdigit function
- istdigit function
- isdigit function
- isdigit_l function
- _ismbcdigit_l function
- _isdigit_l function
ms.assetid: 350b0093-843a-47b0-954e-c1776e8a3853
ms.openlocfilehash: 139453b5f03af2b5ec02db715630adf1f6715716
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343864"
---
# <a name="isdigit-iswdigit-_isdigit_l-_iswdigit_l"></a>isdigit, iswdigit, _isdigit_l, _iswdigit_l

Определяет, представляет ли целое число символ десятичной цифры.

## <a name="syntax"></a>Синтаксис

```C
int isdigit(
   int c
);
int iswdigit(
   wint_t c
);
int _isdigit_l(
   int c,
   _locale_t locale
);
int _iswdigit_l(
   wint_t c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемое целое число.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращается ненулевой, если *c* является особым представлением десятичной цифры. **isdigit** возвращает ненулевое значение, если *c* является десятичной цифрой (0 - 9). **iswdigit** возвращает ненулевое значение, если *c* является широким символом, который соответствует десятично-цифровому символу. Каждая из этих процедур возвращает 0, если *c* не удовлетворяет условию теста.

Версии этих функций, которые имеют **_l** суффикса, используют место, которое передается в вместо текущего локализации для их поведения, зависящем от локализации. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isdigit** и **_isdigit_l** не определено, если *c* не EOF или в диапазоне от 0 до 0xFF, включительно. При использовании библиотеки CRT отладки и *c* не является одним из этих значений, функции повышают утверждение.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istdigit**|**isdigit**|[_ismbcdigit](ismbcalnum-functions.md)|**iswdigit**|
|**_istdigit_l**|**_isdigit_l**|[_ismbcdigit_l](ismbcalnum-functions.md)|**_iswdigit_l**|

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isdigit**|\<ctype.h>|
|**iswdigit**|\<ctype.h> или \<wchar.h>|
|**_isdigit_l**|\<ctype.h>|
|**_iswdigit_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
