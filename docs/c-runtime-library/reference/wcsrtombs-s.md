---
title: wcsrtombs_s
ms.date: 11/04/2016
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
ms.openlocfilehash: 9ece21737b1e0b4d157b241286638ac376843fc6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459063"
---
# <a name="wcsrtombss"></a>wcsrtombs_s

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
Количество символов для преобразования.

*mbstr*<br/>
Адрес буфера для итоговой преобразованной строки многобайтовых символов.

*sizeInBytes*<br/>
Размер в байтах *mbstr* буфера.

*wcstr*<br/>
Указывает на строку расширенных символов, которую необходимо преобразовать.

*count*<br/>
Максимальное число байтов для сохранения в *mbstr* буфера, или [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Указатель на **mbstate_t** объект состояния преобразования.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Возвращаемое значение и **errno**|
|---------------------|------------------------------|
|*mbstr* — **NULL** и *sizeInBytes* > 0|**EINVAL**|
|*wcstr* является **NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если только не *число* — **_TRUNCATE**; см. примечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки и задает **errno** как указано в таблице.

## <a name="remarks"></a>Примечания

**Wcsrtombs_s** функция преобразует строку расширенных символов, на которые указывают *wcstr* в многобайтовые символы, которые хранятся в буфере, на которые указывают *mbstr*, с использованием состояние преобразования, содержащееся в *mbstate*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Число байтов, сохраненных в *mbstr* буфера equals *число*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *число* имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), затем **wcsrtombs_s** преобразование будет помещаются в буфер назначения, по-прежнему предоставляя завершающего нуль Признак конца.

Если **wcsrtombs_s** успешно преобразует исходную строку, он помещает размер в байтах преобразованной строки, включая знак завершения null, в  *&#42;pReturnValue* (предоставленный  *pReturnValue* не **NULL**). Это происходит, даже если *mbstr* аргумент **NULL** и предоставляет способ определить необходимый размер буфера. Обратите внимание, что если *mbstr* — **NULL**, *число* учитывается.

Если **wcsrtombs_s** обнаруживает расширенный символ, не может преобразовать в Многобайтовый символ, он помещается значение -1  *\*pReturnValue*, устанавливает пустую строку в буфер назначения, задает **errno** для **EILSEQ**и возвращает **EILSEQ**.

Если последовательности, на которые указывают *wcstr* и *mbstr* перекрываются, поведение **wcsrtombs_s** не определено. **wcsrtombs_s** влияет категория LC_TYPE текущего языкового стандарта.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не перекрываются и что *число* правильно отражает количество преобразуемых расширенных символов.

**Wcsrtombs_s** функция отличается от [wcstombs_s, _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, в приложении необходимо использовать **wcsrlen** вместо **wcslen**, если в последующем вызове для **wcsrtombs_s** были использованы вместо **wcstombs_s**.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

**Wcsrtombs_s** функция является потокобезопасной, до тех пор, пока не функций в текущем потоке не вызывает **setlocale** пока выполняется данная функция и *mbstate* имеет значение null.

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

void main()
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

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
