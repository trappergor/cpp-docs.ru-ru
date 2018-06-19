---
title: wctomb, _wctomb_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- wctomb
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wide characters, converting
- _wctomb_l function
- wctomb function
- wctomb_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 4a543f0e-5516-4d81-8ff2-3c5206f02ed5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 972d8e3f1798a7498173c3d8b0677bb57231b990
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451543"
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

Если **wctomb** преобразует расширенный символ Многобайтовый символ, он возвращает число байтов (никогда не, превышающий **MB_CUR_MAX**) в расширенных символов. Если *wchar* является нуль-символ Юникода (L '\0'), **wctomb** возвращает 1. Если целевой указатель *mbchar* — **NULL**, **wctomb** возвращает 0. Если преобразование не поддерживается в текущем языковом стандарте, **wctomb** возвращает -1 и **errno** равно **EILSEQ**.

## <a name="remarks"></a>Примечания

**Wctomb** функция преобразует его *wchar* аргумент, соответствующий Многобайтовый символ и сохраняет результат в *mbchar*. Эту функцию можно вызывать из любой точки в любой программе. **wctomb** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_wctomb_l** идентична **wctomb** за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

**wctomb** проверяет свои параметры. Если *mbchar* — **NULL**, вызывается обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** равно **EINVAL** и функция возвращает -1.

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
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
