---
title: wcstombs, _wcstombs_l
ms.date: 11/04/2016
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcstombs
- _wcstombs_l
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
ms.openlocfilehash: b5ee2a0e5636e9c1d1f3fc204b2b6cbf8b733d45
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498985"
---
# <a name="wcstombs-_wcstombs_l"></a>wcstombs, _wcstombs_l

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

*мбстр*<br/>
Адрес последовательности многобайтовых символов.

*вкстр*<br/>
Адрес последовательности расширенных символов.

*count*<br/>
Максимальное количество байтов, которые могут храниться в выходной строке многобайтовых символов.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Если **wcstombs** успешно преобразует многобайтовую строку, она возвращает число байтов, записанных в многобайтовую выходную строку, исключая завершающее значение null (если есть). Если аргумент *мбстр* имеет **значение NULL**, **wcstombs** возвращает требуемый размер строки назначения в байтах. Если **wcstombs** встречает широкий символ, который он не может преобразовать в многобайтовый символ, он возвращает-1 приведение к типу **size_t** и устанавливает значение переводится в **еилсек**.

## <a name="remarks"></a>Примечания

Функция **wcstombs** преобразует строку расширенных символов, на которую указывает *вкстр* , в соответствующие многобайтовые символы и сохраняет результаты в массиве *мбстр* . Параметр *Count* указывает максимальное число байтов, которое может храниться в многобайтовой выходной строке (то есть размер *мбстр*). Как правило, количество байтов, необходимое для преобразования строки расширенных символов, неизвестно. Для некоторых расширенных символов требуется только один байт в выходной строке; для других требуется два байта. При наличии двух байтов в выходной строке многобайтовой кодировки для каждого расширенного символа во входной строке (включая широкий символ null), результат гарантированно подоместится.

Если **wcstombs** обнаруживает символ NULL с расширенными символами (L ' \ 0 ') как до, так и при подсчете, он преобразует его в 8-разрядный 0 и останавливается. Таким словами, Строка многобайтовых символов в *мбстр* завершается нулем, только если **wcstombs** во время преобразования встречает символ расширенного символа null. Если последовательности, на которые указывает *вкстр* и *мбстр* , перекрываются, поведение **wcstombs** не определено.

Если аргумент *мбстр* имеет **значение NULL**, **wcstombs** возвращает требуемый размер строки назначения в байтах.

**wcstombs** проверяет свои параметры. Если *вкстр* имеет **значение NULL**или *Count* больше **INT_MAX**, эта функция вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функция устанавливает **еинвал** и возвращает-1.

**wcstombs** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_wcstombs_l** является идентичным за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение функции **wcstombs** .

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
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
