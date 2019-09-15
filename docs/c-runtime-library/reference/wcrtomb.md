---
title: wcrtomb
ms.date: 11/04/2016
api_name:
- wcrtomb
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcrtomb
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
ms.openlocfilehash: 8d2108b90f6884113f0bd974bf7aa634544adf5f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70945220"
---
# <a name="wcrtomb"></a>wcrtomb

Преобразует расширенный символ в соответствующее представление многобайтового символа. Существует более безопасная версия этой функции; см. раздел [wcrtomb_s](wcrtomb-s.md).

## <a name="syntax"></a>Синтаксис

```C
size_t wcrtomb(
   char *mbchar,
   wchar_t wchar,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcrtomb(
   char (&mbchar)[size],
   wchar_t wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*мбчар*<br/>
Итоговый преобразованный многобайтовый символ.

*wchar*<br/>
Расширенный символ для преобразования.

*мбстате*<br/>
Указатель на объект **mbstate_t** .

## <a name="return-value"></a>Возвращаемое значение

Возвращает число байтов, необходимых для представления преобразованного многобайтового символа, или значение -1, если произошла ошибка.

## <a name="remarks"></a>Примечания

Функция **вкртомб** преобразует расширенный символ, начиная с указанного состояния преобразования, содержащегося в *мбстате*, из значения, содержащегося в параметре *WCHAR*, в адрес, представленный в *мбчар*. Возвращаемое значение — это число байтов, необходимое для представления соответствующего многобайтового символа, однако оно не будет возвращать более **MB_CUR_MAX** байт.

Если *мбстате* имеет значение null, используется внутренний объект **mbstate_t** , содержащий состояние преобразования *мбчар* . Если для последовательности символов *WCHAR* не задано соответствующее представление многобайтового символа, возвращается значение-1, а **для свойства переводится** значение **еилсек**.

Функция **вкртомб** отличается от [wctomb, _wctomb_l](wctomb-wctomb-l.md) с ее возможной перезагрузкой. Состояние преобразования хранится в *мбстате* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать **вксрлен** , а не **wcsnlen**, если последующий вызов **вксртомбс** использовался вместо **wcstombs**.

В C++ эта функция имеет перегрузку шаблона, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

Функция **вкртомб** является потокобезопасной, если ни одна из функций в текущем потоке не вызывает **setlocale** во время выполнения этой функции, а *мбстате* имеет значение null.

## <a name="example"></a>Пример

```C
// crt_wcrtomb.c
// compile with: /W3
// This program converts a wide character
// to its corresponding multibyte character.

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    size_t      sizeOfCovertion = 0;
    mbstate_t   mbstate;
    char        mbStr = 0;
    wchar_t*    wcStr = L"Q";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead
    if (sizeOfCovertion > 0)
    {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wcStr);
        printf(" was converted to the \"%c\" ", mbStr);
        printf("multibyte character.\n");
    }
    else
    {
        printf("No corresponding multibyte character "
               "was found.\n");
    }
}
```

```Output
The corresponding wide character "Q" was converted to the "Q" multibyte character.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcrtomb**|\<wchar.h>|

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
