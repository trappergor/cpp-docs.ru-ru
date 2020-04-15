---
title: _mbsnbcmp, _mbsnbcmp_l
ms.date: 4/2/2020
api_name:
- _mbsnbcmp
- _mbsnbcmp_l
- _o__mbsnbcmp
- _o__mbsnbcmp_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsnbcmp
- tcsnbmp
- _mbsnbcmp_l
- mbsnbcmp_l
- _mbsnbcmp
helpviewer_keywords:
- mbsnbcmp_l function
- mbsnbcmp function
- tcsncmp function
- _mbsnbcmp_l function
- _tcsncmp function
- _mbsnbcmp function
ms.assetid: dbc99e50-cf85-4e57-a13f-067591f18ac8
ms.openlocfilehash: 2334d7755a3eaf3fb973783db17ca398e6b7f0b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340695"
---
# <a name="_mbsnbcmp-_mbsnbcmp_l"></a>_mbsnbcmp, _mbsnbcmp_l

Сравнивает первые **n** байты двух строк мультибайт-символа.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbsnbcmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*string1*, *string2*<br/>
Строки для сравнения.

*count*<br/>
Число байтов для сравнения.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Значение возврата указывает на облачную связь между подстроками *строки1* и *строки2.*

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|*подстрока string1* меньше, чем подстрока *string2.*|
|0|*подстрока string1* идентична *подстроке 2* строки.|
|> 0|*подстрока string1* больше, чем подстрока *string2.*|

По ошибке проверки параметра, **_mbsnbcmp** и **_mbsnbcmp_l** возврата **_NLSCMPERROR,** которая определяется в \<> строки и \<mbstring.h>.

## <a name="remarks"></a>Remarks

**Функции _mbsnbcmp** сравнить не более *первых* байтов в *строках1* и *строке2* и вернуть значение, указывавое связь между подстроками. **_mbsnbcmp** является дело чувствительных версия **_mbsnbicmp**. В отличие от **_mbsnbcoll,** **_mbsnbcmp** не зависит от порядка сопоставления местности. **_mbsnbcmp** распознает последовательности мультибайт-символов в соответствии с текущей многобайтной [страницей кода.](../../c-runtime-library/code-pages.md)

**_mbsnbcmp** напоминает **_mbsncmp,** за исключением того, что **_mbsncmp** сравнивает строки по персонажам, а не байтами.

Значение вывода зависит от LC_CTYPE **параметра** категории локализовать, который определяет свинцовые байты и задние байты мультибайтных символов. Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Функция **_mbsnbcmp** использует текущий локал для этого поведения, зависящем от локального. Функция **_mbsnbcmp_l** идентична, за исключением того, что вместо этого используется параметр *локализации.* Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Если *строка1* или *строка2* является нулевой указателем, эти функции вызывают обработчик параметров недействительного, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, функции возвращаются **_NLSCMPERROR** и **errno** устанавливается **eINVAL.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|---------------------------------------|--------------------|-----------------------|
|**_tcsncmp**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcmp**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|
|**_tcsncmp_l**|[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|**_mbsnbcml**|[wcsncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcmp**|\<mbstring.h>|
|**_mbsnbcmp_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_mbsnbcmp.c
#include <mbstring.h>
#include <stdio.h>

char string1[] = "The quick brown dog jumps over the lazy fox";
char string2[] = "The QUICK brown fox jumps over the lazy dog";

int main( void )
{
   char tmp[20];
   int result;
   printf( "Compare strings:\n          %s\n", string1 );
   printf( "          %s\n\n", string2 );
   printf( "Function: _mbsnbcmp (first 10 characters only)\n" );
   result = _mbsncmp( string1, string2 , 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
   printf( "Function: _mbsnicmp _mbsnicmp (first 10 characters only)\n" );
   result = _mbsnicmp( string1, string2, 10 );
   if( result > 0 )
      _mbscpy_s( tmp, sizeof(tmp), "greater than" );
   else if( result < 0 )
      _mbscpy_s( tmp, sizeof(tmp), "less than" );
   else
      _mbscpy_s( tmp, sizeof(tmp), "equal to" );
   printf( "Result:   String 1 is %s string 2\n\n", tmp );
}
```

### <a name="output"></a>Выходные данные

```Output
Compare strings:
          The quick brown dog jumps over the lazy fox
          The QUICK brown fox jumps over the lazy dog

Function: _mbsnbcmp (first 10 characters only)
Result:   String 1 is greater than string 2

Function: _mbsnicmp _mbsnicmp (first 10 characters only)
Result:   String 1 is equal to string 2
```

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
