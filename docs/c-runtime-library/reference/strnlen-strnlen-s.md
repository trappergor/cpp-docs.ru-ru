---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 11/04/2016
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
ms.openlocfilehash: 960d57ed8c2b1d1dbc6843932b8c76fef35c34a0
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210670"
---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

Получает длину строки, используя текущий или переданный в функцию языковой стандарт. Существуют более безопасные версии функций [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l**, **_mbstrnlen**, и **_mbstrnlen_l** нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка, завершающаяся символом NULL.

*numberOfElements*<br/>
Размер строкового буфера.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Эти функции возвращают число символов в строке, не включая завершающий символ NULL. Если нет завершающего символа null в первых *numberOfElements* байтах строки (или расширенных символов для **wcsnlen**), затем *numberOfElements* возвращается указать на условие ошибки; завершающаяся нулем строки имеют длину, строго меньше, чем *numberOfElements*.

**_mbstrnlen** и **_mbstrnlen_l** возвращают значение -1, если строка содержит недопустимый Многобайтовый символ.

## <a name="remarks"></a>Примечания

> [!NOTE]
> **strnlen** не является заменой для **strlen**; **strnlen** предназначен для использования только для вычисления размера входящих недоверенных данных в буфере известного размера, например, сетевого пакета. **strnlen** вычисляет длину, но не выходит в конец буфера, если строка не определена. В других ситуациях используйте **strlen**. (Относится и к **wcsnlen**, **_mbsnlen**, и **_mbstrnlen**.)

Каждая из этих функций возвращает число символов в *str*, не включая завершающий нуль-символ. Тем не менее **strnlen** и **strnlen_s** интерпретировать строку как строку однобайтовых символов и таким образом, возвращаемое значение всегда равно числу байтов, даже если строка содержит многобайтовые символы. **wcsnlen** и **wcsnlen_s** представляют собой двухбайтовые версии **strnlen** и **strnlen_s** соответственно; аргументы для **wcsnlen**  и **wcsnlen_s** представляют собой строки расширенных символов и число символов выражается в единицах расширенных символов. В противном случае **wcsnlen** и **strnlen** ведут себя одинаково, как **strnlen_s** и **wcsnlen_s**.

**strnlen**, **wcsnlen**, и **_mbsnlen** не проверяют свои параметры. Если *str* — **NULL**, возникает нарушение прав доступа.

**strnlen_s** и **wcsnlen_s** проверяют свои параметры. Если *str* — **NULL**, функция возвращает значение 0.

**_mbstrnlen** также проверяет свои параметры. Если *str* — **NULL**, или если *numberOfElements* больше, чем **INT_MAX**, **_mbstrnlen** создает исключение недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_mbstrnlen** задает **errno** для **EINVAL** и возвращает – 1.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** и **_mbstrnlen** возвращают число многобайтовых символов в строке многобайтовых символов. **_mbsnlen** распознает последовательности многобайтовых символов согласно многобайтовой кодовой странице, или в настоящий момент используется, переданный в функцию языковому стандарту; она не проверяет допустимость многобайтовых символов. **_mbstrnlen** проверяет допустимость многобайтовых символов и распознает последовательности многобайтовых символов. Если строка, которая передается **_mbstrnlen** содержит недопустимый Многобайтовый символ, **errno** присваивается **EILSEQ**.

Выходное значение зависит от настройки **LC_CTYPE** категории языкового стандарта; см. описание [setlocale, _wsetlocale](setlocale-wsetlocale.md) Дополнительные сведения. Версии этих функций идентичны, за исключением того, что без имеют **_l** суффикс используется текущий языковой стандарт для этого поведения, зависящего от языкового стандарта и версий, которые имеют **_l** суффикс Вместо этого используйте переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strnlen**, **strnlen_s**|\<string.h>|
|**wcsnlen**, **wcsnlen_s**|\<string.h> или \<wchar.h>|
|**_mbsnlen**, **_mbsnlen_l**|\<mbstring.h>|
|**_mbstrnlen**, **_mbstrnlen_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
