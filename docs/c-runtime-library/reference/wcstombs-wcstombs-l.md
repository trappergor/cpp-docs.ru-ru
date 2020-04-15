---
title: wcstombs, _wcstombs_l
ms.date: 4/2/2020
api_name:
- wcstombs
- _wcstombs_l
- _o__wcstombs_l
- _o_wcstombs
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
ms.openlocfilehash: fb95c6d73a3979a39995b9104a76fc42ca9e8535
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366711"
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

*mbstr*<br/>
Адрес последовательности многобайтовых символов.

*wcstr*<br/>
Адрес последовательности расширенных символов.

*count*<br/>
Максимальное количество байтов, которые могут храниться в выходной строке многобайтовых символов.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Если **wcstombs** успешно преобразует многобайтную строку, она возвращает количество байтов, написанных в многобайтную строку вывода, исключая терминnull (если таковые имеется). Если аргумент *mbstr* **null,** **wcstombs** возвращает необходимый размер в байтах строки назначения. Если **wcstombs** сталкивается с широким символом, он не может преобразовать в мультибайтный символ, он возвращает -1 литые в введите **size_t** и устанавливает **errno** к **EILSE**.

## <a name="remarks"></a>Remarks

Функция **wcstombs** преобразует строку широкого характера, на которую указывает *wcstr,* в соответствующие мультибайтные символы и сохраняет результаты в массиве *mbstr.* Параметр *подсчета* указывает максимальное количество байтов, которые могут храниться в многобайтной строке вывода (т.е. размер *mbstr).* Как правило, количество байтов, необходимое для преобразования строки расширенных символов, неизвестно. Для некоторых расширенных символов требуется только один байт в выходной строке; для других требуется два байта. Если в многобайтной строке вывода есть два байта для каждого широкого символа в строке ввода (включая широкий символ null), результат гарантированно подходит.

Если **wcstombs** сталкивается с широкохарактерным нулевым персонажем (L'0') либо до, либо когда *происходит подсчет,* он преобразует его в 8-разрядный 0 и останавливается. Таким образом, многобайтная строка символов в *mbstr* непрекращается только в том случае, если **wcstombs** сталкивается с широкохарактерным нулевым характером во время преобразования. Если последовательности, на которые указывают *wcstr* и *mbstr,* перекрываются, поведение **wcstombs** не определено.

Если аргумент *mbstr* **null,** **wcstombs** возвращает необходимый размер в байтах строки назначения.

**wcstombs** проверяет свои параметры. Если *wcstr* **null,** или если *количество* больше, чем **INT_MAX,** эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция устанавливает **errno** к **EINVAL** и возвращает -1.

**wcstombs** использует текущий локал для любого поведения, зависящем от локализуемого; **_wcstombs_l** идентичен, за исключением того, что он использует локал, передаваемый в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ эти функции имеют шаблонные перегрузки, которые вызывают более новые и безопасные аналоги этих функций. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcstombs**|\<stdlib.h>|
|**_wcstombs_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение функции **wcstombs.**

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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
