---
title: isascii, __isascii, iswascii
ms.date: 11/04/2016
api_name:
- iswascii
- __isascii
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
ms.openlocfilehash: b7677819a4b138b08ed4ff97de38c091ce0e94fd
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857792"
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

*c*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм возвращает ненулевое значение, если **c** является определенным представлением символа ASCII. **__isascii** возвращает ненулевое значение, если **c** является символом ASCII (в диапазоне 0x00 – 0x7F). **исвасЦии** возвращает ненулевое значение, если **c** является представлением символа ASCII в расширенном виде символа. Каждая из этих подпрограмм возвращает 0, если **c** не удовлетворяет условию теста.

## <a name="remarks"></a>Заметки

Как **__isascii** , так и **исвасЦии** реализуются в виде макросов, если не определен _CTYPE_DISABLE_MACROS макроса препроцессора.

Для обеспечения обратной **совместимости в качестве** макроса применяется только в том случае, если [ &#95; &#95;STDC&#95; ](../../preprocessor/predefined-macros.md) не определен или определен как 0. в противном случае он не определен.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_istascii**|**__isascii**|**__isascii**|**iswascii**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**__isascii**|C: \<ctype.h><br /><br /> C++: \<cctype> или \<ctype.h>|
|**iswascii**|C: \<wctype.h>, \<ctype.h> или \<wchar.h><br /><br /> C++: \<cwctype>, \<cctype>, \<wctype.h>, \<ctype.h> или \<wchar.h>|

Функции **__isascii** и **исвасЦии** являются специфичными **для Microsoft**. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также:

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Подпрограммы is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
