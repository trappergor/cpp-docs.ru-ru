---
title: wcsrtombs
ms.date: 4/2/2020
api_name:
- wcsrtombs
- _o_wcsrtombs
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
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: af22a7d55c5f4958db6962e98f212fb5bb89e61e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328059"
---
# <a name="wcsrtombs"></a>wcsrtombs

Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Существует более безопасная версия этой функции; см. раздел [wcsrtombs_s](wcsrtombs-s.md).

## <a name="syntax"></a>Синтаксис

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*mbstr*<br/>
Расположение адреса итоговой преобразованной строки многобайтовых символов.

*wcstr*<br/>
Косвенно указывает на расположение преобразуемой строки расширенных символов.

*count*<br/>
Количество символов для преобразования.

*mbstate*<br/>
Указатель на **объект состояния mbstate_t.**

## <a name="return-value"></a>Возвращаемое значение

Возвращает число успешно преобразованных байтов, не включая завершающий байт NULL (если имеется); в противном случае — значение -1, если произошла ошибка.

## <a name="remarks"></a>Remarks

Функция **wcsrtombs** преобразует строку широких символов, начиная с указанного состояния преобразования, содержащегося в *mbstate*, от значений косвенно указал в *wcstr*, в адрес *mbstr*. Преобразование будет продолжаться для каждого символа до: после нулевого прекращения широкий символ встречается, когда не соответствующий символ встречается или когда следующий символ будет превышать предел, содержащийся в *графе*. Если **wcsrtombs** сталкивается с широкохарактерным нулевым персонажем (L'0') либо до, либо когда *происходит подсчет,* он преобразует его в 8-разрядный 0 и останавливается.

Таким образом, многобайтная строка символов в *mbstr* непрекращается только в том случае, если **wcsrtombs** сталкивается с широким символом нулевой характер во время преобразования. Если последовательности, на которые указывают *wcstr* и *mbstr,* перекрываются, поведение **wcsrtombs** не определено. **wcsrtombs** зависит от LC_TYPE категории текущего локаль.

Функция **wcsrtombs** отличается от [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) своей перезапуском. Состояние преобразования хранится в *mbstate* для последующих вызовов к тем же или другим перезажаемым функциям. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение будет использовать **wcsrlen,** а не **wcsnlen**, если последующий вызов **wcsrtombs** были использованы вместо **wcstombs**.

Если аргумент *mbstr* **null,** **wcsrtombs** возвращает необходимый размер в байтах строки назначения. Если *mbstate* является нулевым, используется состояние внутреннего **mbstate_t** преобразования. Если последовательность символов *wchar* не имеет соответствующего мультибайтного представления символов, '1 возвращается, и **errno** устанавливается на **EILSE**.

В C++ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="exceptions"></a>Исключения

Функция **wcsrtombs** является многопоточной безопасной до тех пор, пока ни одна функция в текущем потоке не вызывает **setlocale,** пока эта функция выполняется, и *mbstate* не является недействительным.

## <a name="example"></a>Пример

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
