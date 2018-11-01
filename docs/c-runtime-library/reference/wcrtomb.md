---
title: wcrtomb
ms.date: 11/04/2016
apiname:
- wcrtomb
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
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: a5fad3f41c7ed459a1af3fae7c6a5a85c867d5ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659255"
---
# <a name="wcrtomb"></a>wcrtomb

Преобразует расширенный символ в соответствующее представление многобайтового символа. Существует более безопасная версия этой функции; см. раздел [wcrtomb_s](wcrtomb-s.md).

## <a name="syntax"></a>Синтаксис

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*mbchar*<br/>
Итоговый преобразованный многобайтовый символ.

*wchar*<br/>
Расширенный символ для преобразования.

*mbstate*<br/>
Указатель на **mbstate_t** объекта.

## <a name="return-value"></a>Возвращаемое значение

Возвращает число байтов, необходимых для представления преобразованного многобайтового символа, или значение -1, если произошла ошибка.

## <a name="remarks"></a>Примечания

**Wcrtomb** функция преобразует строку расширенных символов, начиная с указанного состояния преобразования содержащихся в *mbstate*, из значения, содержащегося в *wchar*, в адрес, представленный *mbchar*. Возвращаемое значение — количество байтов, необходимых для представления в соответствующий Многобайтовый символ, но он не вернет более **MB_CUR_MAX** байт.

Если *mbstate* имеет значение null, внутренний **mbstate_t** объект, содержащий состояние преобразования *mbchar* используется. Если последовательность символов *wchar* имеет соответствующие многобайтовые символьном представлении, возвращается значение -1 и **errno** присваивается **EILSEQ**.

**Wcrtomb** функция отличается от [wctomb, _wctomb_l](wctomb-wctomb-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, в приложении необходимо использовать **wcsrlen** вместо **wcsnlen**, если в последующем вызове для **wcsrtombs** были использованы вместо **wcstombs**.

В C++ эта функция имеет перегрузку шаблона, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

**Wcrtomb** функция является потокобезопасной, до тех пор, пока не функций в текущем потоке не вызывает **setlocale** пока выполняется данная функция и while *mbstate* имеет значение null.

## <a name="example"></a>Пример

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
