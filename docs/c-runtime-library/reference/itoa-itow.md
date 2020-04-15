---
title: _itoa, _itow функции
ms.date: 4/2/2020
api_name:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- _o__i64toa
- _o__i64tow
- _o__itoa
- _o__itow
- _o__ltoa
- _o__ltow
- _o__ui64toa
- _o__ui64tow
- _o__ultoa
- _o__ultow
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
ms.openlocfilehash: 0cc084076c5e39843ecc1afa08671ce6b2f06d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342702"
---
# <a name="itoa-_itoa-ltoa-_ltoa-ultoa-_ultoa-_i64toa-_ui64toa-_itow-_ltow-_ultow-_i64tow-_ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

Преобразует целое число в строку. Доступны более безопасные версии этих функций; [видеть _itoa_s, _itow_s функции](itoa-s-itow-s.md).

## <a name="syntax"></a>Синтаксис

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These POSIX versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>Параметры

*value*<br/>
Число, которое требуется преобразовать.

*Буфера*<br/>
Буфер, который удерживает результат преобразования.

*Radix*<br/>
Основание для использования для преобразования *стоимости,* которое должно находиться в диапазоне 2-36.

*Размер*<br/>
Длина буфера в единицах типа символа. Этот параметр выводит из *аргумента буфера* в СЗ.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих функций возвращает указатель в *буфер.* Ошибка не возвращается.

## <a name="remarks"></a>Remarks

**Функции _itoa,** **_ltoa,** **_ultoa,** **_i64toa**и **_ui64toa** преобразуют цифры данного аргумента *значения* в строку символов с нулевым завершением и хранят результат (до 33 символов для **_itoa,** **_ltoa**и **_ultoa**и 65 для **_i64toa** и **_ui64toa)** в *буфере.* Если *радикс* равен 10 и *значение* отрицательное, первым символом**-** сохраненной строки является знак минус (). **_itow,** **_ltow,** **_ultow,** **_i64tow**и **_ui64tow** функции являются широкохарактерными версиями **_itoa,** **_ltoa,** **_ultoa,** **_i64toa**и **_ui64toa**соответственно.

> [!IMPORTANT]
> Эти функции могут писать мимо конца буфера, который слишком мал. Чтобы предотвратить перерасход буфера, убедитесь, что *буфер* достаточно велик, чтобы держать преобразованные цифры плюс задний нулевой символ и знак символа. Неправильное использование этих функций может вызвать серьезные проблемы с безопасностью в коде.

Из-за их потенциала для проблем безопасности, по умолчанию, эти функции вызывают предупреждение об унижании [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **Эта функция или переменная может быть небезопасным. Вместо** этого рассмотрим возможность использования *safe_function.* ** Чтобы отключить изумитель, используйте _CRT_SECURE_NO_WARNINGS.** Мы рекомендуем вам изменить исходный код, чтобы использовать *safe_function,* предложенные в предупреждении. Более безопасные функции не пишут больше символов, чем указанный размер буфера. Для получения дополнительной информации см [_itow_s _itoa_s.](itoa-s-itow-s.md)

Чтобы использовать эти функции без предупреждения об амортизме, определите **_CRT_SECURE_NO_WARNINGS** допроцессорный макрос, прежде чем включать любые заголовки CRT. Это можно сделать в строке команды в запросе команды разработчика, добавив опцию компилятора **/D_CRT_SECURE_NO_WARNINGS** в команду **cl.** В противном случае определите макрос в исходных файлах. Если вы используете предварительно собранные заголовки, определите макрос в верхней части предварительно компилированного заголовка, включите файл *pch.h* *(stdafx.h* в Visual Studio 2017 и ранее). Чтобы определить макрос в исходном коде, используйте **директиву #define,** прежде чем включать любой заголовок CRT, как в этом примере:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

В си-З эти функции имеют перегрузки шаблонов, которые вызывают их более безопасные аналоги. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

POSIX имена **itoa**, **ltoa**, и **ultoa** существуют как псевдонимы для **_itoa,** **_ltoa,** и **_ultoa** функций. Имена POSIX унижаются, поскольку они не соответствуют конвенциям iSO C о конкретных глобальных функциях. По умолчанию эти функции вызывают предупреждение об амортизме [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **Имя POSIX для этого элемента устаревается. Вместо этого используйте конформистическое название ISO C и C е:** *new_name*. Мы рекомендуем вам изменить исходный код, чтобы использовать более безопасные версии этих функций, **_itoa_s,** **_ltoa_s**или **_ultoa_s.** Для получения дополнительной информации см [_itow_s _itoa_s.](itoa-s-itow-s.md)

Для переносимости исходного кода можно предпочесть сохранить имена POSIX в коде. Чтобы использовать эти функции без предупреждения об амортизме, определите как **_CRT_NONSTDC_NO_WARNINGS,** так и **_CRT_SECURE_NO_WARNINGS** предпроцессорные макросы, прежде чем включать любые заголовки CRT. Вы можете сделать это на командной строке в запросе команды разработчика, добавив **/D_CRT_SECURE_NO_WARNINGS** и **/D_CRT_NONSTDC_NO_WARNINGS** варианты компилятора в команду **cl.** В противном случае определите макросы в исходных файлах. Если вы используете предварительно собранные заголовки, определите макросы в верхней части предварительно компилированного заголовка, включите файл. Чтобы определить макросы в исходном коде, используйте **#define** директивы, прежде чем включать любой заголовок CRT, как в этом примере:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>Макросы максимального количества конверсий

Чтобы помочь вам создать безопасные буферы для конверсий, CRT включает в себя несколько удобных макросов. Они определяют размер буфера, необходимого для преобразования максимально возможного значения каждого типа рядов, включая терминатор и символ знака, для нескольких общих баз. Чтобы обеспечить достаточно большой буфер преобразования для получения любого преобразования в базе, указанной *radix,* используйте один из этих определенных макросов при выделении буфера. Это помогает предотвратить ошибки перевыполнения буфера при преобразовании интегральных типов в строки. Эти макросы определяются, когда вы включаете либо stdlib.h или wchar.h в вашем источнике.

Чтобы использовать один из этих макросов в функции преобразования строки, объявить буфер преобразования соответствующего типа символа и использовать макрозначение для типа и базы в качестве буферного измерения. В этой таблице перечислены макросы, подходящие для каждой функции для перечисленных баз:

||||
|-|-|-|
|Функции|radix|Макросы|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

В этом примере используется макрос подсчета конверсий для определения буфера, достаточно большого, чтобы содержать **неподписанный длинный длинный** в базе 2:

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**itoa**, **ltoa**, **ультоа**|\<stdlib.h>|
|**_itoa,** **_ltoa,** **_ultoa,** **_i64toa** **_ui64toa**|\<stdlib.h>|
|**_itow,** **_ltow,** **_ultow,** **_i64tow,** **_ui64tow**|\<stdlib.h> или \<wchar.h>|

Эти функции и макросы специфичны для Майкрософт. Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Этот пример демонстрирует использование некоторых функций преобразования несколько. Обратите внимание на использование **_CRT_SECURE_NO_WARNINGS** макроса, чтобы заставить замолчать предупреждение C4996.

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, _itow_s функции](itoa-s-itow-s.md)<br/>
