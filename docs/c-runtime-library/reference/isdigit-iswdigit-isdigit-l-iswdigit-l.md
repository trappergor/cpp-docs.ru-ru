---
title: isdigit, iswdigit, _isdigit_l, _iswdigit_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _isdigit_l
- iswdigit
- _iswdigit_l
- isdigit
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
- _iswdigit_l
- _isdigit_l
- iswdigit
- isdigit
- _istdigit
- _istdigit_l
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7701b287d6ec4de757249aca5ccd252b38c58267
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401302"
---
# <a name="isdigit-iswdigit-isdigitl-iswdigitl"></a>isdigit, iswdigit, _isdigit_l, _iswdigit_l

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

*c*<br/>
Проверяемое целое число.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждый из этих процедур возвращает ненулевое значение, если *c* — конкретное представление десятичных цифр. **IsDigit** возвращает ненулевое значение, если *c* является десятичной цифрой (0 - 9). **iswdigit** возвращает ненулевое значение, если *c* является расширенным символом, соответствующий символу десятичной цифры. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста.

Версии этих функций, имеющих **_l** суффикс используют языковой стандарт, передаваемый в вместо текущего языкового стандарта для их поведения, зависящего от языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isdigit** и **_isdigit_l** не определено, если *c* не EOF или находится в диапазоне от 0 до 0xFF включительно. При использовании библиотеки отладки CRT и *c* является не один из этих значений, вызываемые функции утверждением.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istdigit**|**isdigit**|[_ismbcdigit](ismbcalnum-functions.md)|**iswdigit**|
|**_istdigit_l**|**_isdigit_l**|[_ismbcdigit_l](ismbcalnum-functions.md)|**_iswdigit_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isdigit**|\<ctype.h>|
|**iswdigit**|\<ctype.h> или \<wchar.h>|
|**_isdigit_l**|\<ctype.h>|
|**_iswdigit_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
