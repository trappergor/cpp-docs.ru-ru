---
title: wcstombs_s, _wcstombs_s_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d392e2a970627cd59d4cb96ae354c3b15406731e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

Преобразует последовательность расширенных символов в соответствующую последовательность многобайтовых символов. Версии функций [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t wcstombs_s(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count
);

errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char *mbstr,
   size_t sizeInBytes,
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
);

template <size_t size>
errno_t wcstombs_s(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count
); // C++ only

template <size_t size>
errno_t _wcstombs_s_l(
   size_t *pReturnValue,
   char (&mbstr)[size],
   const wchar_t *wcstr,
   size_t count,
   _locale_t locale
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
Максимальное число байтов для сохранения в *mbstr* буфер, не включая завершающий символ null или [_TRUNCATE](../../c-runtime-library/truncate.md).

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Возвращаемое значение и **errno**|
|---------------------|------------------------------|
|*mbstr* — **NULL** и *sizeInBytes* > 0|**EINVAL**|
|*wcstr* — **значение NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если не *число* — **_TRUNCATE**; см. примечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает код ошибки и устанавливает **errno** как указано в таблице.

## <a name="remarks"></a>Примечания

**Wcstombs_s** функция преобразует строку расширенных символов, на который указывает *wcstr* в многобайтовые символы, сохраняемые в буфере, на который указывает *mbstr*. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Число байтов, сохраненных в *mbstr* буфера равно *число*.

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *число* имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), затем **wcstombs_s** преобразование строки в виде будет помещаются в буфер назначения, по-прежнему предоставляя место для значения null Признак конца. Если строка усечена, возвращаемым значением является **STRUNCATE**, и преобразование, считается успешным.

Если **wcstombs_s** успешно преобразует исходную строку, он помещает размер в байтах преобразованной строки, включая завершающий символ null в  *&#42;pReturnValue* (предоставленный  *pReturnValue* не **NULL**). Это происходит, даже если *mbstr* аргумент **NULL** и предоставляет способ определить необходимый размер буфера. Обратите внимание, что если *mbstr* — **NULL**, *число* игнорируется.

Если **wcstombs_s** встречает расширенный символ, не может преобразовать Многобайтовый символ, он помещает 0  *&#42;pReturnValue*, устанавливающий буфер назначения на пустую строку, задает **errno**  для **EILSEQ**и возвращает **EILSEQ**.

Если последовательности, на который указывает *wcstr* и *mbstr* перекрываются, то поведение **wcstombs_s** не определено.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не перекрываются и что *число* правильно отражает количество расширенных символов для преобразования.

**wcstombs_s** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта; **_wcstombs_s_l** идентична **wcstombs** за исключением того, что использует переданный языковой стандарт. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Эта программа иллюстрирует поведение **wcstombs_s** функции.

```C
// crt_wcstombs_s.c
// This example converts a wide character
// string to a multibyte character string.
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

#define BUFFER_SIZE 100

int main( void )
{
    size_t   i;
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );
    wchar_t*pWCBuffer = L"Hello, world.";

    printf( "Convert wide-character string:\n" );

    // Conversion
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,
               pWCBuffer, (size_t)BUFFER_SIZE );

    // Output
    printf("   Characters converted: %u\n", i);
    printf("    Multibyte character: %s\n\n",
     pMBBuffer );

    // Free multibyte character buffer
    if (pMBBuffer)
    {
    free(pMBBuffer);
    }
}
```

```Output
Convert wide-character string:
   Characters converted: 14
    Multibyte character: Hello, world.
```

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)<br/>
