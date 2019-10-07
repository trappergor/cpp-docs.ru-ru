---
title: isprint, iswprint, _isprint_l, _iswprint_l
ms.date: 11/04/2016
api_name:
- iswprint
- isprint
- _isprint_l
- _iswprint_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- iswprint
- _istprint
- isprint
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
ms.openlocfilehash: 282b72fcec84f8096ce0d54cd114e756aeafbc85
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953748"
---
# <a name="isprint-iswprint-_isprint_l-_iswprint_l"></a>isprint, iswprint, _isprint_l, _iswprint_l

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

Каждая из этих подпрограмм возвращает ненулевое значение, если *c* является определенным представлением печатного символа. Функция **Print** возвращает ненулевое значение, если *c* является печатаемым символом, включая символ пробела (0x20 – 0x7E). **исвпринт** возвращает ненулевое значение, если *c* является расширенным символом для печати, включая символ расширенного пробела. Каждая из этих подпрограмм возвращает 0, если *c* не удовлетворяет условию теста.

Результат условия теста для этих функций зависит от настройки категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. [в разделе setlocale, _wsetlocale](setlocale-wsetlocale.md) . Версии этих функций, не имеющие суффикса **_l** , используют текущий языковой стандарт для любого поведения, зависящего от языкового стандарта. версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Поведение функций **Print** и **_isprint_l** не определено, если *c* не является EOF или находится в диапазоне от 0 до 0xFF включительно. Если используется библиотека отладки CRT и *c* не является одним из этих значений, функции создают утверждение.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_unicode определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_** **истпринт**|**isprint**|[_ismbcprint](ismbcgraph-functions.md)|**iswprint**|

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
