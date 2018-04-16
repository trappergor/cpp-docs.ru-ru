---
title: strcpy_s, wcscpy_s, _mbscpy_s | Документы Майкрософт
ms.custom: ''
ms.date: 03/22/2086
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcscpy_s
- _mbscpy_s
- strcpy_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strcpy_s
- _mbscpy_s
- _tcscpy_s
- wcscpy_s
dev_langs:
- C++
helpviewer_keywords:
- strcpy_s function
- _tcscpy_s function
- _mbscpy_s function
- copying strings
- strings [C++], copying
- tcscpy_s function
- wcscpy_s function
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8820dbda16d95a201d666a0f25b4e06a6b79c941
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="strcpys-wcscpys-mbscpys"></a>strcpy_s, wcscpy_s, _mbscpy_s

Копирует строку. Это версии функций [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> `_mbscpy_s` не может использоваться в приложениях, запускаемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t strcpy_s(
   char *dest,
   rsize_t dest_size,
   const char *src
);
errno_t wcscpy_s(
   wchar_t *dest,
   rsize_t dest_size,
   const wchar_t *src
);
errno_t _mbscpy_s(
   unsigned char *dest,
   rsize_t dest_size,
   const unsigned char *src
);
```

```cpp
// Template functions are C++ only:
template <size_t size>
errno_t strcpy_s(
   char (&dest)[size],
   const char *src
); // C++ only
template <size_t size>
errno_t wcscpy_s(
   wchar_t (&dest)[size],
   const wchar_t *src
); // C++ only
template <size_t size>
errno_t _mbscpy_s(
   unsigned char (&dest)[size],
   const unsigned char *src
); // C++ only
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Расположение строкового буфера назначения.

*dest_size*<br/>
Размер строкового буфера назначения в **char** единицы для узкой и многобайтовых функций и **wchar_t** единицы для расширенных функций. Это значение должно быть больше нуля и не больше **RSIZE_MAX**.

*src*<br/>
Исходная строка, завершающаяся нулем.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки.

### <a name="error-conditions"></a>Условия ошибок

|*dest*|*dest_size*|*src*|Возвращаемое значение|Содержимое *dest*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL**|any|any|**EINVAL**|не изменено|
|any|any|**NULL**|**EINVAL**|*dest*[0] имеет значение 0|
|any|0 или слишком мал|any|**ERANGE**|*dest*[0] имеет значение 0|

## <a name="remarks"></a>Примечания

`strcpy_s` Функция копируется в адрес *src*, включая завершающий символ null, в расположение, который задается параметром *dest*. Строка назначения должна быть достаточно велика для сохранения исходной строки и завершающего нуля. При перекрытии исходного и конечного буферов поведение `strcpy_s` не определено.

`wcscpy_s` является версией `strcpy_s` с расширенными символами, а `_mbscpy_s` — версией с многобайтовыми символами. Аргументы `wcscpy_s` представляют собой двухбайтовые строки; аргументы `_mbscpy_s` представляют собой многобайтовые строки. В остальном эти три функции ведут себя идентично.

Если *dest* или *src* является пустым указателем, или если размер строки назначения *dest_size* слишком мала, вызывается обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции возвращают **EINVAL** и задайте **errno** для **EINVAL** при *dest* или  *src* является указателем null, и они возвращают **ERANGE** и задайте **errno** для **ERANGE** при строка назначения слишком мал.

После успешного выполнения конечная строка всегда завершается нулем.

В C++ использование данных функций упрощено наличием шаблонных перегрузок, которые могут автоматически определять длину буфера, а также автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Библиотека отладочные версии этих функций сначала заполняют буфер значением 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tcscpy_s`|`strcpy_s`|`_mbscpy_s`|`wcscpy_s`|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`strcpy_s`|\<string.h>|
|`wcscpy_s`|\<string.h> или \<wchar.h>|
|`_mbscpy_s`|\<mbstring.h>|

Эти функции зависят от корпорации Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В отличие от производственного качества кода в этом примере вызывает функции защищенной строки без проверки на наличие ошибок:

```C
// crt_strcpy_s.c
// Compile by using: cl /W4 crt_strcpy_s.c
// This program uses strcpy_s and strcat_s
// to build a phrase.

#include <string.h>     // for strcpy_s, strcat_s
#include <stdlib.h>     // for _countof
#include <stdio.h>      // for printf
#include <errno.h>      // for return values

int main(void)
{
    char string[80];

    strcpy_s(string, _countof(string), "Hello world from ");
    strcat_s(string, _countof(string), "strcpy_s ");
    strcat_s(string, _countof(string), "and ");
    strcat_s(string, _countof(string), "strcat_s!");

    printf("String = %s\n", string);
}
```

```Output
String = Hello world from strcpy_s and strcat_s!
```

При создании кода C++, может быть проще использовать шаблонные версии.

```cpp
// crt_wcscpy_s.cpp
// Compile by using: cl /EHsc /W4 crt_wcscpy_s.cpp
// This program uses wcscpy_s and wcscat_s
// to build a phrase.

#include <cstring>  // for wcscpy_s, wcscat_s
#include <cstdlib>  // for _countof
#include <iostream> // for cout, includes <cstdlib>, <cstring>
#include <errno.h>  // for return values

int main(void)
{
    wchar_t string[80];
    // using template versions of wcscpy_s and wcscat_s:
    wcscpy_s(string, L"Hello world from ");
    wcscat_s(string, L"wcscpy_s ");
    wcscat_s(string, L"and ");
    // of course we can supply the size explicitly if we want to:
    wcscat_s(string, _countof(string), L"wcscat_s!");

    std::wcout << L"String = " << string << std::endl;
}
```

```Output
String = Hello world from wcscpy_s and wcscat_s!
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat, wcscat, _mbscat](../../c-runtime-library/reference/strcat-wcscat-mbscat.md) <br/>
[strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
