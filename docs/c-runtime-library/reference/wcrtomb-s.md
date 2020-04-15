---
title: wcrtomb_s
ms.date: 4/2/2020
api_name:
- wcrtomb_s
- _o_wcrtomb_s
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
- wcrtomb_s
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
ms.openlocfilehash: ee25b18bfbb86b34e46c8c6776e8ab83157613e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328170"
---
# <a name="wcrtomb_s"></a>wcrtomb_s

Преобразует расширенный символ в соответствующее представление многобайтового символа. Версия функции [wcrtomb](wcrtomb.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char *mbchar,
   size_t sizeOfmbchar,
   wchar_t *wchar,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcrtomb_s(
   size_t *pReturnValue,
   char (&mbchar)[size],
   wchar_t *wchar,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Возвращает записанное число символов или –1 в случае возникновения ошибки.

*mbchar*<br/>
Итоговый преобразованный многобайтовый символ.

*размерOfmbchar*<br/>
Размер переменной *mbchar* в байтах.

*Wchar*<br/>
Расширенный символ для преобразования.

*mbstate*<br/>
Указатель на **mbstate_t** объект.

## <a name="return-value"></a>Возвращаемое значение

Возвращает ноль или **значение errno** в случае ошибки.

## <a name="remarks"></a>Remarks

**Функция wcrtomb_s** преобразует широкий символ, начиная с указанного состояния преобразования, содержащегося в *mbstate,* от значения, содержащегося в *wchar,* в адрес, представленный *mbchar.* Значение *pReturnValue* будет значением переоборудованных байтов, но не более **MB_CUR_MAX** байтов, или -1, если произошла ошибка.

Если *mbstate* является нулевым, используется состояние внутреннего **mbstate_t** преобразования. Если символ, содержащийся в *wchar,* не имеет соответствующего мультибайтного символа, значение *pReturnValue* будет -1, и функция вернет **errno** значение **EILSE.**

Функция **wcrtomb_s** отличается от [wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md) ее перезапуском. Состояние преобразования хранится в *mbstate* для последующих вызовов к тем же или другим перезажаемым функциям. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать **wcsrlen,** а не **wcslen,** если последующий вызов **wcsrtombs_s** были использованы вместо **wcstombs_s**.

В C++ использование этой функции упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="exceptions"></a>Исключения

Функция **wcrtomb_s** является многопоточной безопасной до тех пор, пока нет функции в текущем потоке вызовов **setlocale** в то время как эта функция выполняется и *mbstate* является недействительным.

## <a name="example"></a>Пример

```C
// crt_wcrtomb_s.c
// This program converts a wide character
// to its corresponding multibyte character.
//

#include <string.h>
#include <stdio.h>
#include <wchar.h>

int main( void )
{
    errno_t     returnValue;
    size_t      pReturnValue;
    mbstate_t   mbstate;
    size_t      sizeOfmbStr = 1;
    char        mbchar = 0;
    wchar_t*    wchar = L"Q\0";

    // Reset to initial conversion state
    memset(&mbstate, 0, sizeof(mbstate));

    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),
                            *wchar, &mbstate);
    if (returnValue == 0) {
        printf("The corresponding wide character \"");
        wprintf(L"%s\"", wchar);
        printf(" was converted to a the \"%c\" ", mbchar);
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
The corresponding wide character "Q" was converted to a the "Q" multibyte character.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcrtomb_s**|\<wchar.h>|

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbsinit](mbsinit.md)<br/>
