---
title: _strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l
ms.date: 4/2/2020
api_name:
- _mbsnset
- _strnset
- _mbsnset_l
- _wcsnset_l
- _wcsnset
- _strnset_l
- _o__mbsnset
- _o__mbsnset_l
- _o__wcsnset
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsncset_l
- mbsnset_l
- _tcsnset_l
- _fstrnset
- _wcsnset_l
- _ftcsnset
- wcsnset_l
- _mbsnset_l
- _strnset
- _tcsnset
- _strnset_l
- mbsnset
- strnset_l
- _mbsnset
- _wcsnset
- _tcsncset
helpviewer_keywords:
- _wcsnset function
- strnset_l function
- tcsnset function
- tcsncset function
- characters [C++], initializing to formats
- mbsnset function
- _tcsnset_l function
- _mbsnset function
- _strnset function
- _tcsncset_l function
- mbsnset_l function
- _tcsnset function
- initializing characters
- _tcsncset function
- ftcsnset function
- wcsnset_l function
- _ftcsnset function
- _wcsnset_l function
- _fstrnset function
- _mbsnset_l function
- _strnset_l function
- fstrnset function
- strings [C++], initializing
- tcsnset_l function
ms.assetid: 3f306489-5763-48e5-b939-aefee7c94ef5
ms.openlocfilehash: 50b1a5157bd2a60d9819c92103a380ca1005be56
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364423"
---
# <a name="_strnset-_strnset_l-_wcsnset-_wcsnset_l-_mbsnset-_mbsnset_l"></a>_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l

Инициализирует символы строки в конкретный символ. Существуют более безопасные версии этих функций; см. раздел [_strnset_s, _strnset_s_l, _wcsnset_s, _wcsnset_s_l, _mbsnset_s, _mbsnset_s_l](strnset-s-strnset-s-l-wcsnset-s-wcsnset-s-l-mbsnset-s-mbsnset-s-l.md).

> [!IMPORTANT]
> **_mbsnset** и **_mbsnset_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strnset(
   char *str,
   int c,
   size_t count
);
char *_strnset_l(
   char *str,
   int c,
   size_t count,
   locale_t locale
);
wchar_t *_wcsnset(
   wchar_t *str,
   wchar_t c,
   size_t count
);
wchar_t *_wcsnset_l(
   wchar_t *str,
   wchar_t c,
   size_t count,
   _locale_t locale
);
unsigned char *_mbsnset(
   unsigned char *str,
   unsigned int c,
   size_t count
);
unsigned char *_mbsnset_l(
   unsigned char *str,
   unsigned int c,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Строка, которую требуется изменить.

*C*<br/>
Параметр символов.

*count*<br/>
Количество символов для изменения.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на измененную строку.

## <a name="remarks"></a>Remarks

Функция **_strnset** наборы, в лучшем случае, первый *счет* символов *str* до *c* (преобразованы в **символ).** Если *количество* больше, чем длина *str,* длина *str* используется вместо *подсчета.*

**_wcsnset** и **_mbsnset** являются широкохарактерными и многобайтными версиями **_strnset.** Аргументы строки и значение возврата **_wcsnset** являются струнами широкого характера; _mbsnset **являются** многобайтными строками. В остальном эти три функции ведут себя идентично.

**_mbsnset** проверяет свои параметры; если *str* является нулевой указателем, вызовуется обработчик параметров недействительных, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **_mbsnset** возвращает **NULL** и устанавливает **errno** в **EINVAL**. **_strnset** и **_wcsnset** не проверяют их параметры.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnset**|**_strnset**|**_mbsnbset**|**_wcsnset**|
|**_tcsnset_l**|**_strnset_l**|**_mbsnbset_l**|**_wcsnset_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strnset**|\<string.h>|
|**_strnset_l**|\<tchar.h>|
|**_wcsnset**|\<string.h> или \<wchar.h>|
|**_wcsnset_l**|\<tchar.h>|
|**_mbsnset**, **_mbsnset_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strnset.c
// compile with: /W3
#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 characters of string to be *'s */
   printf( "Before: %s\n", string );
   _strnset( string, '*', 4 ); // C4996
   // Note: _strnset is deprecated; consider using _strnset_s
   printf( "After:  %s\n", string );
}
```

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
