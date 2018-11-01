---
title: isalpha, iswalpha, _isalpha_l, _iswalpha_l
ms.date: 11/04/2016
apiname:
- iswalpha
- _iswalpha_l
- isalpha
- _isalpha_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 47b7e43172884524e50e332dcb421e84a99b9806
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591757"
---
# <a name="isalpha-iswalpha-isalphal-iswalphal"></a>isalpha, iswalpha, _isalpha_l, _iswalpha_l

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

*c*<br/>
Проверяемое целое число.

*locale*<br/>
Языковой стандарт, используемый вместо текущего.

## <a name="return-value"></a>Возвращаемое значение

Каждый из этих подпрограмм возвращает ненулевое значение, если *c* — конкретное представление алфавитного символа. **isalpha** возвращает ненулевое значение, если *c* находится в диапазоне A - Z или a – z. **iswalpha** возвращает ненулевое значение только для расширенных символов, для которого [iswupper](isupper-isupper-l-iswupper-iswupper-l.md) или **iswlower** не равно нулю; то есть любые расширенные символы, определяемые реализацией в набор для которых **iswcntrl**, **iswdigit**, **iswpunct**, или **iswspace** имеет ненулевое значение. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста.

В версиях этих функций с **_l** суффикс используется переданный параметр языкового стандарта вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isalpha** и **_isalpha_l** не определено, если *c* не является символом EOF или в диапазоне от 0 до 0xFF включительно. Если используется библиотека отладки CRT и *c* не является одним из следующих значений, функции вызывают утверждение.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istalpha**|**isalpha**|**_ismbcalpha**|**iswalpha**|
|**_istalpha_l**|**_isalpha_l**|**_ismbcalpha_l**|**_iswalpha_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isalpha**|\<ctype.h>|
|**iswalpha**|\<ctype.h> или \<wchar.h>|
|**_isalpha_l**|\<ctype.h>|
|**_iswalpha_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
