---
title: _mbsnbcat_s, _mbsnbcat_s_l
ms.date: 4/2/2020
api_name:
- _mbsnbcat_s_l
- _mbsnbcat_s
- _o__mbsnbcat_s
- _o__mbsnbcat_s_l
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
helpviewer_keywords:
- _tcsncat function
- mbsnbcat_s function
- _mbsnbcat_s function
- _mbsnbcat_s_l function
- _tcsncat_s_l function
- tcsncat_s_l function
- mbsnbcat_s_l function
- tcsncat function
ms.assetid: 2c9e9be7-d979-4a54-8ada-23428b6648a9
ms.openlocfilehash: b4a9540025ad039458203eec1cc950187b6316a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340787"
---
# <a name="_mbsnbcat_s-_mbsnbcat_s_l"></a>_mbsnbcat_s, _mbsnbcat_s_l

Приложения к многобайтовой строке символа, в лучшем случае, первые **n** байты другой строки мультибайт-символа. Это версии функций [_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _mbsnbcat_s(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count
);
errno_t _mbsnbcat_s_l(
   unsigned char *dest,
   size_t sizeInBytes,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcat_s(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcat_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Многобайтовая строка назначения, завершаемая нуль-символом.

*размерInBytes*<br/>
Размер *буфера dest* в байтах.

*src*<br/>
Исходная многобайтовая строка, завершаемая нуль-символом.

*count*<br/>
Количество байтов от *src* к придатку к *dest*.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|**Dest**|*размерInBytes*|*src*|Возвращаемое значение|
|------------|-------------------|-----------|------------------|
|**Null**|any|any|**EINVAL**|
|Любой|<= 0|any|**EINVAL**|
|Любой|any|**Null**|**EINVAL**|

Если возникает какое-либо из условий ошибки, функция создает ошибку недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если ошибка обработана, функция возвращает **EINVAL** и устанавливает **errno** **в EINVAL.**

## <a name="remarks"></a>Remarks

Функция **_mbsnbcat_s** прилагает к *dest,* в лучшем случае, первые *байты от* *src*. Если байт, который сразу же предшествует нулевой характер в *dest* является свинца байт, он перезаписан первоначальным байтом *src*. В противном случае, начальный байт *src* перезаписывает прекращающийся нулевой характер *dest*. Если null байт появляется в *src* до *подсчета* байтов, приложено, **_mbsnbcat_s** придатков все байты от *src*, до нулевой характер. Если *количество* больше, чем длина *src,* длина *src* используется вместо *кол- и.* Результирующая строка завершается нуль-символом. Если копирование производится между перекрывающимися строками, поведение не определено.

На значение вывода влияет настройка **LC_CTYPE** категории локализуем; см [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. Версии этих функций идентичны, за исключением того, что те, которые не имеют **_l** суффикс использовать текущий локали и те, которые имеют **_l** суффикс вместо использования параметра локали, который прошел дюйма Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные функции могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

Отладка библиотеки версии этих функций сначала заполнить буфер с 0xFE. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat_s**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_s_l**|**_strncat_s_l**|**_mbsnbcat_s_l**|**_wcsncat_s_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcat_s**|\<mbstring.h>|
|**_mbsnbcat_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
