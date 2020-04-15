---
title: strcspn, wcscspn, _mbscspn, _mbscspn_l
ms.date: 4/2/2020
api_name:
- _mbscspn_l
- wcscspn
- _mbscspn
- strcspn
- _o__mbscspn
- _o__mbscspn_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strcspn
- _mbscspn
- wcscspn
- _ftcscspn
- _tcscspn
helpviewer_keywords:
- strings [C++], searching
- ftcscspn function
- strcspn function
- _mbscspn function
- mbscspn_l function
- wcscspn function
- tcscspn function
- _ftcscspn function
- _mbscspn_l function
- mbscspn function
- _tcscspn function
ms.assetid: f73f51dd-b533-4e46-ba29-d05c553708a6
ms.openlocfilehash: 2ba3c2941736d185ad93c7c6e44cb83c82ebb478
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358879"
---
# <a name="strcspn-wcscspn-_mbscspn-_mbscspn_l"></a>strcspn, wcscspn, _mbscspn, _mbscspn_l

Возвращает индекс первого вхождения в строке символа, который относится к набору символов.

> [!IMPORTANT]
> **_mbschr** и **_mbschr_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
size_t strcspn(
   const char *str,
   const char *strCharSet
);
size_t wcscspn(
   const wchar_t *str,
   const wchar_t *strCharSet
);
size_t _mbscspn(
   const unsigned char *str,
   const unsigned char *strCharSet
);
size_t _mbscspn_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Строка, завершающаяся символом NULL, для поиска.

*strCharSet*<br/>
Набор символов, завершающийся символом NULL.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Эти функции возвращают индекс первого символа в *str,* который находится в *strCharSet.* Если ни один из символов в *str* находится в *strCharSet,* то значение возврата длина *str*.

Нет зарезервированных возвращаемых значений для указания ошибки.

## <a name="remarks"></a>Remarks

**wcscspn** и **_mbscspn** являются широкохарактерными и мультибайт-символами версий **strcspn.** Аргументы **wcscspn** являются широкохарактерные строки; _mbscspn **являются** многобайтными строками.

**_mbscspn** проверяет свои параметры. Если *str* или *strCharSet* является нулевой указателем, вызовуется обработчик параметров недействительных, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функция возвращает 0 и устанавливает **errno** к **EINVAL**. **strcspn** и **wcscspn** не проверяют их параметры. В остальном эти три функции ведут себя идентично.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscspn**|**strcspn**|**_mbscspn**|**wcscspn**|
|Недоступно|Недоступно|**_mbscspn_l**|Недоступно|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strcspn**|\<string.h>|
|**wcscspn**|\<string.h> или \<wchar.h>|
|**_mbscspn**, **_mbscspn_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strcspn.c

#include <string.h>
#include <stdio.h>

void test( const char * str, const char * strCharSet )
{
   int pos = strcspn( str, strCharSet );
   printf( "strcspn( \"%s\", \"%s\" ) = %d\n", str, strCharSet, pos );
}

int main( void )
{
   test( "xyzbxz", "abc" );
   test( "xyzbxz", "xyz" );
   test( "xyzbxz", "no match" );
   test( "xyzbxz", "" );
   test( "", "abc" );
   test( "", "" );
}
```

```Output
strcspn( "xyzbxz", "abc" ) = 3
strcspn( "xyzbxz", "xyz" ) = 0
strcspn( "xyzbxz", "no match" ) = 6
strcspn( "xyzbxz", "" ) = 6
strcspn( "", "abc" ) = 0
strcspn( "", "" ) = 0
```

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
