---
title: wctomb_s, _wctomb_s_l
ms.date: 4/2/2020
api_name:
- _wctomb_s_l
- wctomb_s
- _o__wctomb_s_l
- _o_wctomb_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wctomb_s
- _wctomb_s_l
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
ms.openlocfilehash: 1ddc9a991f28c4a2ea491f3ddd04d78f6345e255
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367249"
---
# <a name="wctomb_s-_wctomb_s_l"></a>wctomb_s, _wctomb_s_l

Преобразует расширенный символ в соответствующий многобайтовый символ. Версия функции [wctomb, _wctomb_l](wctomb-wctomb-l.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wctomb_s(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar
);
errno_t _wctomb_s_l(
   int *pRetValue,
   char *mbchar,
   size_t sizeInBytes,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*pRetValue*<br/>
Число байтов или код, указывающий результат.

*mbchar*<br/>
Адрес последовательности многобайтовых символов.

*размерInBytes*<br/>
Размер буфера *mbchar*.

*Wchar*<br/>
Расширенный символ.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

Ситуации, которые могут привести к ошибке

|*mbchar*|*размерInBytes*|Возвращаемое значение|*pRetValue*|
|--------------|-------------------|------------------|-----------------|
|**Null**|> 0|**EINVAL**|не изменено|
|any|>**Int_max**|**EINVAL**|не изменено|
|any|слишком мало|**EINVAL**|не изменено|

Если выполняется какое-либо из приведенных выше условий возникновения ошибки, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если исполнение разрешено продолжать, **wctomb** возвращает **EINVAL** и устанавливает **errno** к **EINVAL**.

## <a name="remarks"></a>Remarks

Функция **wctomb_s** преобразует свой аргумент *wchar* в соответствующий мультибайтный символ и сохраняет результат на *mbchar.* Эту функцию можно вызывать из любой точки в любой программе.

Если **wctomb_s** преобразует широкий символ в мультибайтный символ, он помещает количество байтов (что никогда не превышает **MB_CUR_MAX)** в широком характере в целый тег, на который указывает *pRetValue.* Если *wchar* является широкохарактерным нулевым персонажем (L'0'), **wctomb_s** заполняет *pRetValue* с 1. Если целевой указатель *mbchar* **является NULL,** **wctomb_s** ставит 0 в *pRetValue*. Если преобразование невозможно в текущем локаль, **wctomb_s** ставит -1 в *pRetValue*.

**wctomb_s** использует текущий локал для информации, зависящей от локализации; **_wctomb_s_l** идентичен, за исключением того, что он использует локал, передаваемый в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wctomb_s**|\<stdlib.h>|
|**_wctomb_s_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение функции **wctomb.**

```cpp
// crt_wctomb_s.cpp
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
    int i;
    wchar_t wc = L'a';
    char *pmb = (char *)malloc( MB_CUR_MAX );

    printf_s( "Convert a wide character:\n" );
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );
    printf_s( "   Characters converted: %u\n", i );
    printf_s( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
