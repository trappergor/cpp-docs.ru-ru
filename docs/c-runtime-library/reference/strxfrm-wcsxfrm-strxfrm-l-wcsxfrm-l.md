---
title: strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l
ms.date: 4/2/2020
api_name:
- strxfrm
- _wcsxfrm_l
- _strxfrm_l
- wcsxfrm
- _o__strxfrm_l
- _o__wcsxfrm_l
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strxfrm
- _tcsxfrm
- wcsxfrm
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
ms.openlocfilehash: aabe7e7c2e44f558b936e0fd4c6fa4a85dc582f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362970"
---
# <a name="strxfrm-wcsxfrm-_strxfrm_l-_wcsxfrm_l"></a>strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l

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

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Возвращает длину преобразованной строки, не считая завершающий нуль-символ. Если значение возврата больше или равно *количеству,* содержание *strDest* непредсказуемо. При ошибке каждая функция устанавливает **errno** и возвращает **INT_MAX.** Для недействительного персонажа **errno** устанавливается на **EILSE**.

## <a name="remarks"></a>Remarks

Функция **strxfrm** преобразует строку, на которую указывает *strSource,* в новую сопоставленную форму, которая хранится в *strDest.* Не более чем *считать* символы, в том числе нулевой характер, преобразуются и помещены в результирующую строку. Преобразование производится с использованием настройки **LC_COLLATE** категории локализующих. Для получения дополнительной информации о **LC_COLLATE,** [см. setlocale](setlocale-wsetlocale.md). **strxfrm** использует текущий локал для своего поведения, зависящем от локализуем; **_strxfrm_l** идентичен, за исключением того, что он использует локал, передаваемый в вместо текущего локаль. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

После преобразования вызов **к strcmp** с двумя преобразованными строками дает результаты, идентичные результатам вызова **strcoll,** применяемым к исходным двум строкам. Как и в случае с **strcoll** и **stricoll,** **strxfrm** автоматически обрабатывает строки мультибайт-символа по мере необходимости.

**wcsxfrm** является широкохарактерным вариантом **strxfrm;** строка аргументы **wcsxfrm** являются широкохарактерные указатели. Для **wcsxfrm**, после преобразования строки, вызов **wcscmp** с двумя преобразованными строками дает результаты идентичны тем, что вызов **wcscoll** применяется к исходным двум строкам. **wcsxfrm** и **strxfrm** ведут себя одинаково иначе. **wcsxfrm** использует текущий локал для своего поведения, зависящем от локализуем; **_wcsxfrm_l** использует местность, передаваемую в вместо текущего локализу.

Эти функции проверяют свои параметры. Если *strSource* является нулевой указатель, или *strDest* является **null** указатель (если счет равна нулю), или если *количество* больше, чем **INT_MAX,** недействительным обработчик параметров вызывается, как описано в [параметр проверки](../../c-runtime-library/parameter-validation.md) . Если выполнение разрешено продолжать, эти функции установить **errno** **eINVAL** и вернуть **INT_MAX**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsxfrm**|**strxfrm**|**strxfrm**|**wcsxfrm**|
|**_tcsxfrm_l**|**_strxfrm_l**|**_strxfrm_l**|**_wcsxfrm_l**|

В языковом стандарте "C" порядок символов в наборе символов (кодировка ASCII) совпадает с лексикографическим порядком символов. Однако в других языковых стандартах порядок символов в наборе символов может отличаться от лексикографического порядка. Например, в некоторых европейских языковых стандартах символ a (значение 0x61) предшествует символу &\#x00E4; (значение 0xE4) в наборе символов, но ä предшествует символу a лексикографически.

В лоцах, для которых набор символов и порядок лексикографического характера отличаются, используйте **strxfrm** на исходных строках, а затем **strcmp** на результирующих строках для получения лексикографического сравнения строк в соответствии с текущим настройками **LC_COLLATE** категории. Таким образом, для сравнения двух строк лексикографически в вышеуказанном месте, используйте **strxfrm** на исходных строках, а затем **strcmp** на результирующих строках. Кроме того, вы можете использовать **strcoll,** а не **strcmp** на исходных строк.

**strxfrm** в основном обертка вокруг [LCMapString](/windows/win32/api/winnls/nf-winnls-lcmapstringw) с **LCMAP_SORTKEY**.

Значением следующего выражения является размер массива, необходимого для удержания преобразования **строки строки строки строки strxfrm:**

`1 + strxfrm( NULL, string, 0 )`

Только в локаль "C" **strxfrm** эквивалентен следующему:

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

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcoll Functions](../../c-runtime-library/strcoll-functions.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
