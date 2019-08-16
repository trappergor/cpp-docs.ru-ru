---
title: _strrev, _wcsrev, _mbsrev, _mbsrev_l
ms.date: 11/04/2016
apiname:
- _wcsrev
- _mbsrev
- _strrev
- _mbsrev_l
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
- _strrev
- _ftcsrev
- _tcsrev
- mbsrev
- mbsrev_l
- _wcsrev_fstrrev
- _mbsrev
helpviewer_keywords:
- _mbsrev_l function
- characters [C++], switching
- _mbsrev function
- strrev function
- _ftcsrev function
- strings [C++], reversing
- wcsrev function
- _strrev function
- mbsrev_l function
- reversing characters in strings
- ftcsrev function
- characters [C++], reversing order
- _wcsrev function
- mbsrev function
- tcsrev function
- _tcsrev function
ms.assetid: 87863e89-4fa0-421c-af48-25d8516fe72f
ms.openlocfilehash: 36cbf78c4645c22209892be77f3bf77e7c93c76b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499416"
---
# <a name="_strrev-_wcsrev-_mbsrev-_mbsrev_l"></a>_strrev, _wcsrev, _mbsrev, _mbsrev_l

Меняет порядок символов в строке на обратный.

> [!IMPORTANT]
> **_mbsrev** и **_mbsrev_l** нельзя использовать в приложениях, которые выполняются в среда выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strrev(
   char *str
);
wchar_t *_wcsrev(
   wchar_t *str
);
unsigned char *_mbsrev(
   unsigned char *str
);
unsigned char *_mbsrev_l(
   unsigned char *str,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка для преобразования, завершающаяся символом NULL.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на измененную строку. Нет зарезервированных возвращаемых значений для указания ошибки.

## <a name="remarks"></a>Примечания

Функция **_strrev** изменяет порядок символов в *str*на обратный. Завершающий нуль-символ остается на месте. **_wcsrev** и **_mbsrev** — это версии **_strrev**для расширенных символов и многобайтовых символов. Аргументы и возвращаемое значение **_wcsrev** являются строками расширенных символов. **_mbsrev** являются строками многобайтовых символов. Для **_mbsrev**порядок байтов в каждом многобайтовой кодировке в *str* не изменяется. В остальном эти три функции ведут себя идентично.

**_mbsrev** проверяет свои параметры. Если либо *строка1* , либо *строка2* являются пустым указателем, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_mbsrev** возвращает **значение NULL** и устанавливает в качестве значения по **еинвал**. **_strrev** и **_wcsrev** не проверяют свои параметры.

На выходное значение влияет параметр категории **LC_CTYPE** языкового стандарта. Дополнительные сведения см. [в разделе setlocale, _wsetlocale](setlocale-wsetlocale.md) . Версии этих функций идентичны, за исключением того, что у тех, кто не имеет суффикса **_l** , используется текущий языковой стандарт, а вместо этого суффикс **_l** использует переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!IMPORTANT]
> Эти функции могут быть подвержены угрозам переполнения буфера. Переполнение буфера можно использовать для атак на систему, поскольку оно может привести к несанкционированному повышению уровня привилегий. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsrev**|**_strrev**|**_mbsrev**|**_wcsrev**|
|**Н/Д**|**Н/Д**|**_mbsrev_l**|**Н/Д**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_strrev**|\<string.h>|
|**_wcsrev**|\<string.h> или \<wchar.h>|
|**_mbsrev**, **_mbsrev_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strrev.c
// This program checks a string to see
// whether it is a palindrome: that is, whether
// it reads the same forward and backward.
//

#include <string.h>
#include <stdio.h>

int main( void )
{
   char* string = "Able was I ere I saw Elba";
   int result;

   // Reverse string and compare (ignore case):
   result = _stricmp( string, _strrev( _strdup( string ) ) );
   if( result == 0 )
      printf( "The string \"%s\" is a palindrome\n", string );
   else
      printf( "The string \"%s\" is not a palindrome\n", string );
}
```

```Output
The string "Able was I ere I saw Elba" is a palindrome
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
