---
title: mbrlen
ms.date: 4/2/2020
api_name:
- mbrlen
- _o_mbrlen
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrlen
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
ms.openlocfilehash: 7503de22a8310335ddd678335916d3e74dab6e70
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340989"
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

*Ул*<br/>
Указатель на следующий байт для проверки в строке многобайтовых символов.

*count*<br/>
Максимальное число байтов для проверки.

*mbstate*<br/>
Указатель на текущее состояние смещения начального байта *str*.

## <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

|||
|-|-|
0|Следующий *счет* или меньше байтов завершают мультибайтный символ, представляющий широкий нулевой символ.
1 для *подсчета,* включительно|Следующий *счет* или меньше байтов завершают действительный мультибайтный символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ.
(size_t)(-2)|Следующие байты *подсчета* способствуют неполному, но потенциально допустимому многобайтному символу, и все *байты подсчета* были обработаны.
(size_t)(-1)|Произошла ошибка кодирования. Следующий *подсчет* или меньше байт не способствуют полному и допустимому мультибайтному символу. В этом случае **errno** устанавливается в EILSE, а состояние преобразования в *mbstate* не уточняется.

## <a name="remarks"></a>Remarks

Функция **mbrlen** проверяет в большинстве *количество* байтов, начиная с байта, на который *указывается str,* чтобы определить количество байтов, которые необходимы для завершения следующего мультибайтного символа, включая любые последовательности сдвигов. Это эквивалентно вызову, `mbrtowc(NULL, str, count, &mbstate)` где *mbstate* является либо пользовательским **mbstate_t** объектом, либо статическим внутренним объектом, предоставленным библиотекой.

Функция **mbrlen** сохраняет и использует состояние смещения неполного мультибайтного символа в параметре *mbstate.* Это дает **mbrlen** возможность перезагрузки в середине мультибайт характер, если это необходимо, изучение в *большинстве подсчет* байтов. Если *mbstate* является нулевой указатель, **mbrlen** использует внутренний, статический **mbstate_t** объект для хранения состояния сдвиг. Поскольку внутренний **mbstate_t** объект не является безопасным для потока, мы рекомендуем вам всегда выделять и передавать свой собственный параметр *mbstate.*

Функция **mbrlen** отличается от [_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md) своей перезапуском. Состояние сдвига хранится в *mbstate* для последующих вызовов к тем же или другим перезажаемым функциям. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение должно использовать **wcsrlen** вместо **wcslen,** если последующий вызов **wcsrtombs** используется вместо **wcstombs**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|Неприменимо|Неприменимо|**mbrlen**|Неприменимо|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbrlen**|\<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Этот пример показывает, как интерпретация мультибайтных символов зависит от текущей страницы кода, и демонстрирует возможность возобновления **mbrlen**.

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

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
