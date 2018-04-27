---
title: wcstombs, _wcstombs_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- wcstombs
- _wcstombs_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
caps.latest.revision: 30
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45286f9b7b344292318eaf46500c9a24e0b8488d
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l

Преобразует последовательность расширенных символов в соответствующую последовательность многобайтовых символов. Существуют более безопасные версии этих функций; см. раздел [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md).

## <a name="syntax"></a>Синтаксис

```C
size_t wcstombs(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count
);
size_t _wcstombs_l(
   char *mbstr,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
size_t wcstombs(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only
template <size_t size>
size_t _wcstombs_l(
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*mbstr*<br/>
Адрес последовательности многобайтовых символов.

*wcstr*<br/>
Адрес последовательности расширенных символов.

*count*<br/>
Максимальное количество байтов, которые могут храниться в выходной строке многобайтовых символов.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Если **wcstombs** успешно преобразовывает строку многобайтовых, он возвращает число байтов, записанных в выходной строке многобайтовых символов, исключая конечный символ **NULL** (если таковые имеются). Если *mbstr* аргумент **NULL**, **wcstombs** возвращает необходимый размер строки назначения в байтах. Если **wcstombs** встречает расширенный символ, не может преобразовать Многобайтовый символ, возвращается значение -1, приведенное к типу **size_t** и задает **errno** для **EILSEQ** .

## <a name="remarks"></a>Примечания

**Wcstombs** функция преобразует строку расширенных символов, на который указывает *wcstr* в соответствующие многобайтовые символы и сохраняет результаты в *mbstr* массива. *Число* параметр указывает максимальное число байтов, которые могут храниться в выходной строке многобайтовых символов (то есть размер *mbstr*). Как правило, количество байтов, необходимое для преобразования строки расширенных символов, неизвестно. Для некоторых расширенных символов требуется только один байт в выходной строке; для других требуется два байта. При наличии двух байтов в выходной строке многобайтовых символов на каждый расширенный символ во входной строке (включая расширенный символ **NULL**), результат гарантированно поместится.

Если **wcstombs** встречает нуль-символ Юникода (L '\0'), перед или после *число* символов, она преобразовывает его в 8-битный 0 и останавливается. Таким образом, строка многобайтовых символов *mbstr* завершается нуль символом только в том случае, если **wcstombs** встречает расширенный символ null во время преобразования. Если последовательности, на который указывает *wcstr* и *mbstr* перекрываются, то поведение **wcstombs** не определено.

Если *mbstr* аргумент **NULL**, **wcstombs** возвращает необходимый размер строки назначения в байтах.

**wcstombs** проверяет свои параметры. Если *wcstr* — **NULL**, или если *число* больше, чем **INT_MAX**, эта функция вызывает обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функция устанавливает **errno** для **EINVAL** и возвращает значение -1.

**wcstombs** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_wcstombs_l** идентична за исключением того, что она использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение **wcstombs** функции.

```C
// crt_wcstombs.c
// compile with: /W3
// This example demonstrates the use
// of wcstombs, which converts a string
// of wide characters to a string of
// multibyte characters.

#include <stdlib.h>
#include <stdio.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t  count;
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t *pWCBuffer = L"Hello, world.";

    printf("Convert wide-character string:\n" );

    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996
    // Note: wcstombs is deprecated; consider using wcstombs_s instead
    printf("   Characters converted: %u\n",
            count );
    printf("    Multibyte character: %s\n\n",
           pMBBuffer );

    free(pMBBuffer);
}
```

```Output
Convert wide-character string:
   Characters converted: 13
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
