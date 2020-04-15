---
title: wcstombs_s, _wcstombs_s_l
ms.date: 4/2/2020
api_name:
- _wcstombs_s_l
- wcstombs_s
- _o__wcstombs_s_l
- _o_wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
ms.openlocfilehash: c20066cddb3f28d31d2964ec720b64ed49836f65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328049"
---
# <a name="wcstombs_s-_wcstombs_s_l"></a>wcstombs_s, _wcstombs_s_l

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
Размер байтов преобразованной строки, включая нулевой терминатор.

*mbstr*<br/>
Адрес буфера для итоговой преобразованной строки многобайтовых символов.

*размерInBytes*<br/>
Размер байтов буфера *mbstr.*

*wcstr*<br/>
Указывает на строку расширенных символов, которую необходимо преобразовать.

*count*<br/>
Максимальное количество байтов для хранения в буфере *mbstr,* не включая термин null, или [_TRUNCATE.](../../c-runtime-library/truncate.md)

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Значение возврата и **errno**|
|---------------------|------------------------------|
|*mbstr* **является NULL** и *размерInBytes* > 0|**EINVAL**|
|*wcstr* является **NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы содержать преобразованную строку (если *не считать* **_TRUNCATE;** см. Замечания ниже)|**ERANGE**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, функция возвращает код ошибки и устанавливает **errno,** как указано в таблице.

## <a name="remarks"></a>Remarks

Функция **wcstombs_s** преобразует строку широких символов, на которые указывает *wcstr,* в мультибайтные символы, хранящиеся в буфере, на который указывает *mbstr.* Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился расширенный нуль-символ.

- Встретился расширенный символ, который не может быть преобразован.

- Количество байтов, хранящихся в буфере *mbstr,* *равнозначно.*

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *счет* является специальным значением [_TRUNCATE,](../../c-runtime-library/truncate.md)то **wcstombs_s** преобразует столько строки, сколько будет вписываться в буфер назначения, в то же время оставляя место для нулевой терминатор. Если строка усечена, значение возврата является **STRUNCATE,** и преобразование считается успешным.

Если **wcstombs_s** успешно преобразует строку исходного кода, она помещает размер байтов преобразованной строки, включая терминатор null, в *&#42;pReturnValue* (при условии, *что pReturnValue* не является **NULL).** Это происходит даже в том случае, если аргумент *mbstr* является **NULL** и предоставляет способ определения требуемого размера буфера. Обратите внимание, что если *mbstr* является **NULL,** *количество* игнорируется.

Если **wcstombs_s** встречает широкий символ, он не может преобразовать в мультибайтный символ, он помещает 0 в *&#42;pReturnValue,* устанавливает буфер назначения на пустую строку, устанавливает **errno** к **EILSE**, и возвращает **EILSE**.

Если последовательности, указанные *wcstr* и *mbstr,* перекрываются, поведение **wcstombs_s** не определено.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не пересекаются, и это *количество* правильно отражает количество широких символов для преобразования.

**wcstombs_s** использует текущий локал для любого поведения, зависящем от локализуемого; **_wcstombs_s_l** идентичен **wcstombs,** за исключением того, что он использует локал, передаваемый вместо этого. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**wcstombs_s**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wctomb_s, _wctomb_s_l](wctomb-s-wctomb-s-l.md)<br/>
[WideCharToMultiByte](/windows/win32/api/stringapiset/nf-stringapiset-widechartomultibyte)<br/>
