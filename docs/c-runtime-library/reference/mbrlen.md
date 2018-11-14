---
title: mbrlen
ms.date: 11/04/2016
apiname:
- mbrlen
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
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: ec9079b9b164e2b609a956ddf3a75cd42923bafc
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518338"
---
# <a name="mbrlen"></a>mbrlen

Определяют число байтов, необходимое для составления многобайтового символа в текущем языковом стандарте, с возможностью перезапуска в середине многобайтового символа.

## <a name="syntax"></a>Синтаксис

```C
size_t mbrlen(
   const char * str,
   size_t count,
   mbstate_t * mbstate
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Указатель на следующий байт для проверки в строке многобайтовых символов.

*count*<br/>
Максимальное число байтов для проверки.

*mbstate*<br/>
Указатель на текущее состояние сдвига начального байта *str*.

## <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

|||
|-|-|
0|Следующий *число* или менее байт составляют Многобайтовый символ, представляющий расширенный нуль-символ.
1, чтобы *число*включительно|Следующий *число* или менее байт составляют допустимый Многобайтовый символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ.
(size_t)(-2)|Следующий *число* байт складываются в неполный, но потенциально допустимый Многобайтовый символ и все *число* байт были обработаны.
(size_t)(-1)|Произошла ошибка кодирования. Следующий *число* или меньше байт не составляют полный и допустимый Многобайтовый символ. В этом случае **errno** имеет значение EILSEQ и состояние преобразования в *mbstate* не определен.

## <a name="remarks"></a>Примечания

**Mbrlen** функция проверяет не более *число* байт, начиная с байта, на которые указывают *str* для определения числа байтов, которые необходимы для завершения следующей Многобайтовый символ, включая любые последовательности сдвигов. Это свойство эквивалентно вызову `mbrtowc(NULL, str, count, &mbstate)` где *mbstate* — это либо предоставленный пользователем **mbstate_t** объекта или статический внутренний объект, предоставляемый библиотекой.

**Mbrlen** функция сохраняет и использует состояние сдвига неполного многобайтового символа в *mbstate* параметра. Это дает **mbrlen** возможностью перезапуска в середине многобайтового символа при необходимости проверки до *число* байтов. Если *mbstate* является пустым указателем, **mbrlen** использует внутренний статичный **mbstate_t** объект для хранения состояния сдвига. Так как внутренний **mbstate_t** объект не является потокобезопасным, мы рекомендуем всегда сохранять и передавать собственный *mbstate* параметра.

**Mbrlen** функция отличается от [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) возможностью перезапуска. Состояние сдвига хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, в приложении необходимо использовать **wcsrlen** вместо **wcslen** при последующем вызове **wcsrtombs** используется вместо **wcstombs**.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|Неприменимо|Неприменимо|**mbrlen**|Неприменимо|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В этом примере показано, как Интерпретация многобайтовых символов зависит от текущей кодовой странице и демонстрирует возможность возобновления **mbrlen**.

```C
// crt_mbrlen.c
// Compile by using: cl crt_mbrlen.c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

size_t Example(const char * pStr)
{
    size_t      charLen = 0;
    size_t      charCount = 0;
    mbstate_t   mbState = {0};

    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&
            charLen != (size_t)-1)
    {
        if (charLen != (size_t)-2) // if complete mbcs char,
        {
            charCount++;
        }
    }
    return (charCount);
}

int main( void )
{
    int         cp;
    size_t      charCount = 0;
    const char  *pSample =
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";

    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);

    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale
    _setmbcp(932); // and Japanese multibyte code page
    cp = _getmbcp();
    charCount = Example(pSample);
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",
        cp, pSample, charCount);
}
```

```Output

Code page: 0
é╨éτé¬é╚: Shift-jis hiragana.
Character count: 29

Code page: 932
????: Shift-jis hiragana.
Character count: 25
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
