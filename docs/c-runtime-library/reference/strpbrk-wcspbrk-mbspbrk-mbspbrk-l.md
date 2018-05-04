---
title: strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbspbrk
- wcspbrk
- _mbspbrk_l
- strpbrk
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
- _fstrpbrk
- _mbspbrk
- strpbrk
- _tcspbrk
- _ftcspbrk
- wcspbrk
dev_langs:
- C++
helpviewer_keywords:
- fstrpbrk function
- _ftcspbrk function
- _mbspbrk_l function
- strpbrk function
- _fstrpbrk function
- mbspbrk function
- characters [C++], scanning strings
- _tcspbrk function
- wcspbrk function
- ftcspbrk function
- character sets [C++], scanning strings for characters
- strings [C++], scanning
- tcspbrk function
- _mbspbrk function
- mbspbrk_l function
ms.assetid: 80b504f7-a167-4dde-97ad-4ae3000dc810
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd62d95e971ac5fd927cce1b7b4eb600ebcf7df6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="strpbrk-wcspbrk-mbspbrk-mbspbrkl"></a>strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

Сканирует строки на наличие символов в указанных наборах символов.

> [!IMPORTANT]
> **_mbspbrk** и **_mbspbrk_l** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *strpbrk(
   const char *str,
   const char *strCharSet
); // C only
char *strpbrk(
   char *str,
   const char *strCharSet
); // C++ only
const char *strpbrk(
   const char *str,
   const char *strCharSet
); // C++ only
wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C only
wchar_t *wcspbrk(
   wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
const wchar_t *wcspbrk(
   const wchar_t *str,
   const wchar_t *strCharSet
); // C++ only
unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C only
unsigned char *_mbspbrk(
   unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
const unsigned char *_mbspbrk(
   const unsigned char *str,
   const unsigned char *strCharSet
); // C++ only
unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C only
unsigned char *_mbspbrk_l(
   unsigned char *str,
   const unsigned char *strCharSet,
   _locale_t locale
); // C++ only
const unsigned char *_mbspbrk_l(
   const unsigned char *str,
   const unsigned char* strCharSet,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка для поиска, завершающаяся символом NULL.

*strCharSet*<br/>
Набор символов, завершающийся символом NULL.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на первое вхождение любого символа от *strCharSet* в *str*, или **NULL** указателя, если две строковые аргументы имеют общие никакие символы.

## <a name="remarks"></a>Примечания

**Strpbrk** функция возвращает указатель на первое вхождение символа в *str* , входящего в набор символов в *strCharSet*. Поиск не включает завершающие нуль-символы.

**wcspbrk** и **_mbspbrk** версии Юникода и многобайтовых символов **strpbrk**. Аргументы и возвращаемое значение **wcspbrk** являются двухбайтовые строки; аргументы **_mbspbrk** представляют собой строки многобайтовых символов.

**_mbspbrk** проверяет свои параметры. Если *str* или *strCharSet* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **_mbspbrk** возвращает **NULL** и задает **errno** для **EINVAL**. **strpbrk** и **wcspbrk** не проверяют свои параметры. В остальном эти три функции ведут себя идентично.

**_mbspbrk** аналогичен **_mbscspn** за исключением того, **_mbspbrk** возвращает указатель, а не значение типа [size_t](../../c-runtime-library/standard-types.md).

В языке C, эти функции принимают ** const ** указатель для первого аргумента. В языке C++ доступны две перегрузки. Перегрузка, используя указатель на ** const ** возвращает указатель на **const **; версия, которая принимает указатель на отличных**const ** возвращает указатель на отличных**const **. Макрос **_CRT_CONST_CORRECT_OVERLOADS** определяется, если оба **const ** и не-** const ** доступны версии этих функций. Если требуется не**const ** поведение для обоих перегрузки C++ определения символа **_CONST_RETURN**.

Выходное значение зависит от настройки **LC_CTYPE** категории задании языкового стандарта; Дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без **_l** используют текущий языковой стандарт для поведения, зависящего от языкового стандарта; версии с **_l** суффикс идентичен, за исключением того, что он использует параметр языкового стандарта Переданный. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcspbrk**|**strpbrk**|**_mbspbrk**|**wcspbrk**|
|**Н/Д**|**Н/Д**|**_mbspbrk_l**|**Н/Д**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strpbrk**|\<string.h>|
|**wcspbrk**|\<string.h> или \<wchar.h>|
|**_mbspbrk**, **_mbspbrk_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_strpbrk.c

#include <string.h>
#include <stdio.h>

int main( void )
{
   char string[100] = "The 3 men and 2 boys ate 5 pigs\n";
   char *result = NULL;

   // Return pointer to first digit in "string".
   printf( "1: %s\n", string );
   result = strpbrk( string, "0123456789" );
   printf( "2: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "3: %s\n", result++ );
   result = strpbrk( result, "0123456789" );
   printf( "4: %s\n", result );
}
```

```Output
1: The 3 men and 2 boys ate 5 pigs

2: 3 men and 2 boys ate 5 pigs

3: 2 boys ate 5 pigs

4: 5 pigs
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strchr, wcschr, _mbschr, _mbschr_l](strchr-wcschr-mbschr-mbschr-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
