---
title: wcsrtombs_s
ms.date: 4/2/2020
api_name:
- wcsrtombs_s
- _o_wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: 71a2206df9d3afb64fcaf62848988cf116d9071f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328110"
---
# <a name="wcsrtombs_s"></a>wcsrtombs_s

Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Версия функции [wcsrtombs](wcsrtombs.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
errno_t wcsrtombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Размер байтов преобразованной строки, включая нулевой терминатор.

*mbstr*<br/>
Адрес буфера для итоговой преобразованной строки многобайтовых символов.

*размерInBytes*<br/>
Размер байтов буфера *mbstr.*

*wcstr*<br/>
Указывает на строку расширенных символов, которую необходимо преобразовать.

*count*<br/>
Максимальное количество байтов, которые будут храниться в буфере *mbstr,* или [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Указатель на **объект состояния mbstate_t.**

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Значение возврата и **errno**|
|---------------------|------------------------------|
|*mbstr* **является NULL** и *размерInBytes* > 0|**EINVAL**|
|*wcstr* является **NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы содержать преобразованную строку (если *не считать* **_TRUNCATE;** см. Замечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, функция возвращает код ошибки и устанавливает **errno,** как указано в таблице.

## <a name="remarks"></a>Remarks

Функция **wcsrtombs_s** преобразует строку широких символов, на которые указывает *wcstr,* в мультибайтные символы, хранящиеся в буфере, на который указывает *mbstr,* используя состояние преобразования, содержащееся в *mbstate.* Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Количество байтов, хранящихся в буфере *mbstr,* *равнозначно.*

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *подсчет* является специальным значением [_TRUNCATE,](../../c-runtime-library/truncate.md)то **wcsrtombs_s** преобразует столько строки, сколько будет вписываться в буфер назначения, в то же время оставляя место для нулевой терминатор.

Если **wcsrtombs_s** успешно преобразует строку исходного кода, она помещает размер байтов преобразованной строки, включая терминатор, в *&#42;pReturnValue* (при условии, *что pReturnValue* не является **NULL).** Это происходит даже в том случае, если аргумент *mbstr* является **NULL** и предоставляет способ определения требуемого размера буфера. Обратите внимание, что если *mbstr* является **NULL,** *количество* игнорируется.

Если **wcsrtombs_s** встречает широкий символ, он не может преобразовать в мультибайтный символ, он помещает -1 в * \*pReturnValue,* устанавливает буфер назначения на пустую строку, устанавливает **errno** к **EILSE**и возвращает **EILSE**.

Если последовательности, указанные *wcstr* и *mbstr,* перекрываются, поведение **wcsrtombs_s** не определено. **wcsrtombs_s** зависит от LC_TYPE категории текущего локализации.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не пересекаются, и это *количество* правильно отражает количество широких символов для преобразования.

Функция **wcsrtombs_s** отличается от [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) ее перезапуском. Состояние преобразования хранится в *mbstate* для последующих вызовов к тем же или другим перезажаемым функциям. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать **wcsrlen,** а не **wcslen,** если последующий вызов **wcsrtombs_s** были использованы вместо **wcstombs_s**.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="exceptions"></a>Исключения

Функция **wcsrtombs_s** является многопоточной безопасной до тех пор, пока нет функции в текущем потоке вызовов **setlocale** в то время как эта функция выполняется и *mbstate* является недействительным.

## <a name="example"></a>Пример

```cpp
// crt_wcsrtombs_s.cpp
//
// This code example converts a wide
// character string into a multibyte
// character string.
//

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
    errno_t         err;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);
    if (err == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfully converted.\n" );
    }
}
```

```Output
The string was successfully converted.
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcsrtombs_s**|\<wchar.h>|

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
