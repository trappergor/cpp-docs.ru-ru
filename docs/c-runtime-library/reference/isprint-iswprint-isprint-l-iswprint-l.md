---
title: isprint, iswprint, _isprint_l, _iswprint_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
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
- iswprint
- _istprint
- isprint
dev_langs:
- C++
helpviewer_keywords:
- _istprint function
- iswprint function
- _iswprint_l function
- isprint_l function
- istprint function
- isprint function
- iswprint_l function
- _isprint_l function
ms.assetid: a8bbcdb0-e8d0-4d8c-ae4e-56d3bdee6ca3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af7cd775c22d4d34d7a6512938a0f612c3708940
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="isprint-iswprint-isprintl-iswprintl"></a>isprint, iswprint, _isprint_l, _iswprint_l

Определяет, представляет ли целое число печатный символ.

## <a name="syntax"></a>Синтаксис

```C
int isprint(
   int c
);
int iswprint(
   wint_t c
);
int _isprint_l(
   int c,
   _locale_t locale
);
int _iswprint_l(
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

Каждый из этих процедур возвращает ненулевое значение, если *c* — конкретное представление печатные символы. **isprint** возвращает ненулевое значение, если *c* является печатные символы — это включает символ пробела (0x20 — 0x7E). **iswprint** возвращает ненулевое значение, если *c* является печатный расширенный символ — это включает свободное место, расширенный символ. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста.

Результат условия теста для этих функций зависит от **LC_CTYPE** категории языкового стандарта см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. Версии этих функций, у которых нет **_l** используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; версии, которые имеют **_l** суффиксом идентичны, за исключением того, что они используют языковой стандарт, который передается в. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение **isprint** и **_isprint_l** не определено, если *c* не EOF или находится в диапазоне от 0 до 0xFF включительно. При использовании библиотеки отладки CRT и *c* является не один из этих значений, вызываемые функции утверждением.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_unicode определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **istprint**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isprint**|\<ctype.h>|
|**iswprint**|\<ctype.h> или \<wchar.h>|
|**_isprint_l**|\<ctype.h>|
|**_iswprint_l**|\<ctype.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
