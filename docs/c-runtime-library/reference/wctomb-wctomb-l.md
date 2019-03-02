---
title: wctomb, _wctomb_l
ms.date: 11/04/2016
apiname:
- _wctomb_l
- wctomb
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wctomb
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
ms.openlocfilehash: df0abdd644027f9bab8cd177dfd4d0af4c98df35
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210488"
---
# <a name="wctomb-wctombl"></a>wctomb, _wctomb_l

Преобразует расширенный символ в соответствующий многобайтовый символ. Существуют более безопасные версии этих функций; см. раздел [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md).

## <a name="syntax"></a>Синтаксис

```C
int wctomb(
   char *mbchar,
   wchar_t wchar
);
int _wctomb_l(
   char *mbchar,
   wchar_t wchar,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*mbchar*<br/>
Адрес последовательности многобайтовых символов.

*wchar*<br/>
Расширенный символ.

## <a name="return-value"></a>Возвращаемое значение

Если **wctomb** преобразует расширенный символ в Многобайтовый символ, он возвращает число байтов (которое больше никогда не **MB_CUR_MAX**) в расширенном символе. Если *wchar* является нуль-символ Юникода (L '\0'), **wctomb** возвращает значение 1. Если целевой указатель *mbchar* — **NULL**, **wctomb** возвращает 0. Если преобразование не поддерживается в текущем языковом стандарте, **wctomb** возвращает -1 и **errno** присваивается **EILSEQ**.

## <a name="remarks"></a>Примечания

**Wctomb** функция преобразует его *wchar* аргумент в соответствующий Многобайтовый символ и сохраняет результат в *mbchar*. Эту функцию можно вызывать из любой точки в любой программе. **wctomb** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_wctomb_l** идентична **wctomb** за исключением того, что она использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

**wctomb** проверяет свои параметры. Если *mbchar* — **NULL**, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL** и функция возвращает -1.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wctomb**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение функции wctomb.

```cpp
// crt_wctomb.cpp
// compile with: /W3
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int i;
   wchar_t wc = L'a';
   char *pmb = (char *)malloc( MB_CUR_MAX );

   printf( "Convert a wide character:\n" );
   i = wctomb( pmb, wc ); // C4996
   // Note: wctomb is deprecated; consider using wctomb_s
   printf( "   Characters converted: %u\n", i );
   printf( "   Multibyte character: %.1s\n\n", pmb );
}
```

```Output
Convert a wide character:
   Characters converted: 1
   Multibyte character: a
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[WideCharToMultiByte](/windows/desktop/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
