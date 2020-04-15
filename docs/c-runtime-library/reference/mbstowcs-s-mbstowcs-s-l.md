---
title: mbstowcs_s, _mbstowcs_s_l
ms.date: 4/2/2020
api_name:
- _mbstowcs_s_l
- mbstowcs_s
- _o__mbstowcs_s_l
- _o_mbstowcs_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
ms.openlocfilehash: 07d694a7430f23e2f9600a5d2b147bcee2ef0e09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338810"
---
# <a name="mbstowcs_s-_mbstowcs_s_l"></a>mbstowcs_s, _mbstowcs_s_l

Преобразует последовательность многобайтовых символов в соответствующую последовательность расширенных символов. Это версии функции [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Количество символов для преобразования.

*wcstr*<br/>
Адрес буфера для результирующей преобразованной строки расширенных символов.

*sizeInWords*<br/>
Размер буфера *wcstr* в словах.

*mbstr*<br/>
Адрес последовательности многобайтовых символов, заканчивающейся нуль-символом.

*count*<br/>
Максимальное количество широких символов для хранения в буфере *wcstr,* не включая термины null или [_TRUNCATE.](../../c-runtime-library/truncate.md)

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Нуль в случае успеха или код ошибки в случае неудачи.

|Условие ошибки|Значение возврата и **errno**|
|---------------------|------------------------------|
|*wcstr* **является NULL** и *размерInWords* > 0|**EINVAL**|
|*mbstr* является **NULL**|**EINVAL**|
|Буфер назначения слишком мал, чтобы содержать преобразованную строку (если *не считать* **_TRUNCATE;** см. Замечания ниже)|**ERANGE**|
|*wcstr* не **является НУАИКИНеСлова** 0 *sizeInWords*|**EINVAL**|

Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, функция возвращает код ошибки и устанавливает **errno,** как указано в таблице.

## <a name="remarks"></a>Remarks

Функция **mbstowcs_s** преобразует строку мультибайтных символов, на которые указывает *mbstr,* в широкие символы, хранящиеся в буфере, на который указывает *wcstr.* Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.

- Встретился многобайтовый символ null.

- Встретился недопустимый многобайтовый символ.

- Количество широких символов, хранящихся в буфере *wcstr,* *равному количеству.*

Строка назначения всегда завершается нуль-символом (даже в случае ошибки).

Если *подсчет* является специальным значением [_TRUNCATE,](../../c-runtime-library/truncate.md)то **mbstowcs_s** преобразует столько строки, сколько будет вписываться в буфер назначения, оставляя место для нулевого терминатора.

Если **mbstowcs_s** успешно преобразует строку исходного кода, она помещает размер в широкие символы преобразованной строки, включая нулевой терминатор, в *&#42;pReturnValue* (при условии, *что pReturnValue* не является **NULL).** Это происходит даже в том случае, если аргумент *wcstr* является **NULL** и предоставляет способ определения требуемого размера буфера. Обратите внимание, что если *wcstr* **является NULL,** *количество* игнорируется, и *sizeInWords* должно быть 0.

Если **mbstowcs_s** сталкивается с недействительным мультибайтным персонажем, он помещает 0 в *&#42;pReturnValue,* устанавливает буфер назначения на пустую строку, устанавливает **errno** к **EILSE**и возвращает **EILSE**.

Если последовательности, указанные *mbstr* и *wcstr,* перекрываются, поведение **mbstowcs_s** не определено.

> [!IMPORTANT]
> Убедитесь, что *wcstr* и *mbstr* не пересекаются, и это *количество* правильно отражает количество мультибайт символов для преобразования.

**mbstowcs_s** использует текущий локал для любого поведения, зависящем от локализуемого; **_mbstowcs_s_l** идентичен, за исключением того, что он использует локал, передаваемый в вместо. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
