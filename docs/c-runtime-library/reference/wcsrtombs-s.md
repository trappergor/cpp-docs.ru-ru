---
title: wcsrtombs_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f8649ab5039cc08734860b5a7e788b5d14f7de8
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
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
|*wcstr* — **значение NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если не *число* — **_TRUNCATE**; см. примечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки и устанавливает **errno** как указано в таблице.

## <a name="remarks"></a>Примечания

**Wcsrtombs_s** функция преобразует строку расширенных символов, на который указывает *wcstr* в многобайтовые символы, сохраняемые в буфере, на который указывает *mbstr*, с использованием состояние преобразования, содержащееся в *mbstate*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Число байтов, сохраненных в *mbstr* буфера равно *число*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *число* имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), затем **wcsrtombs_s** преобразование строки в виде будет помещаются в буфер назначения, по-прежнему предоставляя место для значения null Признак конца.

Если **wcsrtombs_s** успешно преобразует исходную строку, он помещает размер в байтах преобразованной строки, включая завершающий символ null в  *&#42;pReturnValue* (предоставленный  *pReturnValue* не **NULL**). Это происходит, даже если *mbstr* аргумент **NULL** и предоставляет способ определить необходимый размер буфера. Обратите внимание, что если *mbstr* — **NULL**, *число* игнорируется.

Если **wcsrtombs_s** встречает расширенный символ, не может преобразовать Многобайтовый символ, он помещается значение -1  *\*pReturnValue*, устанавливающий буфер назначения на пустую строку, задает **errno** для **EILSEQ**и возвращает **EILSEQ**.

Если последовательности, на который указывает *wcstr* и *mbstr* перекрываются, то поведение **wcsrtombs_s** не определено. **wcsrtombs_s** влияет категория LC_TYPE текущего языкового стандарта.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не перекрываются и что *число* правильно отражает количество расширенных символов для преобразования.

**Wcsrtombs_s** функция отличается от [wcstombs_s _wcstombs_s_l](wcstombs-s-wcstombs-s-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, приложение будет использовать **wcsrlen** вместо **wcslen**, если в последующем вызове **wcsrtombs_s** были использованы вместо **wcstombs_s**.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Исключения

**Wcsrtombs_s** функция является потокобезопасной, при условии, что ни одна из функций в текущем потоке вызывает **setlocale** во время выполнения этой функции и *mbstate* имеет значение null.

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
