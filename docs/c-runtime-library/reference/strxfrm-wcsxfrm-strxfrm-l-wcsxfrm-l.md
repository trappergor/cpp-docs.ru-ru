---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
dev_langs:
- C++
helpviewer_keywords:
- strxfrm_l function
- _tcsxfrm function
- _strxfrm_l function
- strxfrm function
- wcsxfrm_l function
- wcsxfrm function
- string comparison [C++], transforming strings
- tcsxfrm function
- strings [C++], comparing locale
- _wcsxfrm_l function
ms.assetid: 6ba8e1f6-4484-49aa-83b8-bc2373187d9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc9746d2c98f1799cbdd244e7fc4d465fd705fa
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
---
# <a name="strxfrm-wcsxfrm-strxfrml-wcsxfrml"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

Преобразует строку на основе данных языкового стандарта.

## <a name="syntax"></a>Синтаксис

```C
size_t strxfrm(
   char *strDest,
   const char *strSource,
   size_t count
);
size_t wcsxfrm(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count
);
size_t _strxfrm_l(
   char *strDest,
   const char *strSource,
   size_t count,
   _locale_t locale
);
size_t wcsxfrm_l(
   wchar_t *strDest,
   const wchar_t *strSource,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*strDest*<br/>
Конечная строка.

*strSource*<br/>
Исходная строка.

*count*<br/>
Максимальное количество символов для размещения в *strDest*.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает длину преобразованной строки, не считая завершающий нуль-символ. Если возвращаемое значение больше или равно *число*, содержимое *strDest* непредсказуем. При возникновении ошибки каждая функция устанавливает **errno** и возвращает **INT_MAX**. Для недопустимый символ **errno** равно **EILSEQ**.

## <a name="remarks"></a>Примечания

**Strxfrm** функция преобразует строку, на который указывает *strSource* в новую упорядоченную форму, которая хранится в *strDest*. Не более чем *число* преобразуется и размещается в результирующую строку символов, включая символ null. Преобразование осуществляется с помощью языкового стандарта **LC_COLLATE** параметра категории. Дополнительные сведения о **LC_COLLATE**, в разделе [setlocale](setlocale-wsetlocale.md). **strxfrm** использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; **_strxfrm_l** идентична за исключением того, что она использует переданный параметр языкового стандарта вместо текущего языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

После преобразования вызов **strcmp** с двумя преобразованными строками дает результаты, которые идентичны результату вызова **strcoll** применены к двум исходным строкам. Как и в **strcoll** и **stricoll**, **strxfrm** автоматически обрабатывает строки многобайтовых символов соответствующим образом.

**wcsxfrm** — это двухбайтовая версия **strxfrm**; строковые аргументы функции **wcsxfrm** являются указателями расширенных символов. Для **wcsxfrm**после того, как преобразовать строку, вызов **wcscmp** с двумя преобразованными строками дает результаты, которые идентичны результату вызова **wcscoll** применены к двум исходным строкам. **wcsxfrm** и **strxfrm** ведут себя идентично. **wcsxfrm** использует текущий языковой стандарт для поведения, зависящего от языкового стандарта; **_wcsxfrm_l** использует переданный параметр языкового стандарта вместо текущего языкового стандарта.

Эти функции проверяют свои параметры. Если *strSource* является пустым указателем, или *strDest* — **NULL** указатель (если значение счетчика равно нулю), или если *число* больше, чем **INT_MAX**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, эти функции устанавливают **errno** для **EINVAL** и возвращают **INT_MAX**.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

В языковом стандарте "C" порядок символов в наборе символов (кодировка ASCII) совпадает с лексикографическим порядком символов. Однако в других языковых стандартах порядок символов в наборе символов может отличаться от лексикографического порядка. Например, в некоторых европейских языковых стандартах символ a (значение 0x61) предшествует символу &\#x00E4; (значение 0xE4) в наборе символов, но ä предшествует символу a лексикографически.

В регионах, для которых отличаются символов в наборе и лексикографическим порядком символов, используйте **strxfrm** для исходных строк и затем **strcmp** на результирующих строках для лексикографического строка сравнения согласно текущего языкового стандарта **LC_COLLATE** параметра категории. Таким образом, чтобы сравнить две строки лексикографически в приведенном ранее языковом стандарте, используйте **strxfrm** для исходных строк, затем **strcmp** для результирующих строк. Кроме того, можно использовать **strcoll** вместо **strcmp** для исходных строк.

**strxfrm** по сути является оболочкой вокруг [LCMapString](http://msdn.microsoft.com/library/windows/desktop/dd318700) с **LCMAP_SORTKEY**.

Значение следующего выражения — это размер массива, необходимого для хранения **strxfrm** преобразования исходной строки:

`1 + strxfrm( NULL, string, 0 )`

В языковом стандарте «C», **strxfrm** эквивалентно следующему:

```C
strncpy( _string1, _string2, _count );
return( strlen( _string1 ) );
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**strxfrm**|\<string.h>|
|**wcsxfrm**|\<string.h> или \<wchar.h>|
|**_strxfrm_l**|\<string.h>|
|**_wcsxfrm_l**|\<string.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Функции strcoll](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
