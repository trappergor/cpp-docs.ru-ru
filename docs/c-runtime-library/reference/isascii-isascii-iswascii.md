---
title: isascii, __isascii, iswascii
ms.date: 11/04/2016
apiname:
- iswascii
- __isascii
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
ms.openlocfilehash: d150e7bb335dc77ed86f445128eebf97b8be5ac3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433663"
---
# <a name="isascii-isascii-iswascii"></a>isascii, __isascii, iswascii

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

*c*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Каждый из этих подпрограмм возвращает ненулевое значение, если **c** — конкретное представление символа ASCII. **__isascii** возвращает ненулевое значение, если **c** представляет собой символ ASCII (в диапазоне 0x00 – 0x7F). **iswascii** возвращает ненулевое значение, если **c** представляет собой символ ASCII расширенных символов. Каждая из этих подпрограмм возвращает 0, если **c** не удовлетворяет условию теста.

## <a name="remarks"></a>Примечания

Оба **__isascii** и **iswascii** реализованы в виде макросов, если определен макрос препроцессора _CTYPE_DISABLE_MACROS.

Для обеспечения обратной совместимости **isascii** реализуется как макрос, только если [ &#95; &#95;STDC&#95; &#95; ](../../preprocessor/predefined-macros.md) не определен или определен как 0; в противном случае оно будет неопределенным.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isascii**, **__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h> или \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> или \<wchar.h>|

**Isascii**, **__isascii** и **iswascii** функции только к системам Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
