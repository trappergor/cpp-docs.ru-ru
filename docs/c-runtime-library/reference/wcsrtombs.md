---
title: wcsrtombs
ms.date: 11/04/2016
apiname:
- wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: 46ef195ec4685c327c4b5951ec44e5c363214b59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494423"
---
# <a name="wcsrtombs"></a>wcsrtombs

Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Существует более безопасная версия этой функции; см. раздел [wcsrtombs_s](wcsrtombs-s.md).

## <a name="syntax"></a>Синтаксис

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*mbstr*<br/>
Расположение адреса итоговой преобразованной строки многобайтовых символов.

*wcstr*<br/>
Косвенно указывает на расположение преобразуемой строки расширенных символов.

*count*<br/>
Количество символов для преобразования.

*mbstate*<br/>
Указатель на **mbstate_t** объект состояния преобразования.

## <a name="return-value"></a>Возвращаемое значение

Возвращает число успешно преобразованных байтов, не включая завершающий байт NULL (если имеется); в противном случае — значение -1, если произошла ошибка.

## <a name="remarks"></a>Примечания

**Wcsrtombs** функция преобразует строку расширенных символов, начиная с указанного состояния преобразования содержащихся в *mbstate*, из значений, косвенно указанных в *wcstr*, в адрес *mbstr*. Преобразование будет продолжаться для каждого символа до: после завершения расширенный символ задано значение NULL, при обнаружении несоответствующий символ или следующий символ может превысить ограничение, указанное в *число*. Если **wcsrtombs** встречает нуль-символ Юникода (L '\0'), до или после *число* происходит, она преобразовывает его в 8-битный 0 и останавливается.

Таким образом, строка многобайтовых символов *mbstr* завершается нуль символом только в том случае, если **wcsrtombs** встречает расширенный символ нуль-символ во время преобразования. Если последовательности, на которые указывают *wcstr* и *mbstr* перекрываются, поведение **wcsrtombs** не определено. **wcsrtombs** влияет категория LC_TYPE текущего языкового стандарта.

**Wcsrtombs** функция отличается от [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, в приложении необходимо использовать **wcsrlen** вместо **wcsnlen**, если в последующем вызове для **wcsrtombs** были использованы вместо **wcstombs**.

Если *mbstr* аргумент **NULL**, **wcsrtombs** возвращает необходимый размер строки назначения в байтах. Если *mbstate* имеет значение null, внутренний **mbstate_t** используется состояние преобразования. Если последовательность символов *wchar* имеет соответствующие многобайтовые символьном представлении, возвращается значение -1 и **errno** присваивается **EILSEQ**.

В C++ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

**Wcsrtombs** функция является потокобезопасной, до тех пор, пока не функций в текущем потоке не вызывает **setlocale** пока выполняется данная функция и *mbstate* не равно null.

## <a name="example"></a>Пример

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
