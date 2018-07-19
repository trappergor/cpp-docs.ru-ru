---
title: _mbsnbcpy_s, _mbsnbcpy_s_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbcpy_s_l
- _mbsnbcpy_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsnbcpy_s_l
- _mbsnbcpy_s
- mbsnbcpy_s
- _mbsnbcpy_s_l
dev_langs:
- C++
helpviewer_keywords:
- _mbsnbcpy_s function
- tcsncpy_s function
- mbsnbcpy_s_l function
- _tcsncpy_s_l function
- mbsnbcpy_s function
- tcsncpy_s_l function
- _mbsnbcpy_s_l function
- _tcsncpy_s function
ms.assetid: dfff64ab-fe6f-49c4-99ba-75014e2b0cd6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9475609d304b6a3e49c2f71073c4d06c0380160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404121"
---
# <a name="mbsnbcpys-mbsnbcpysl"></a>_mbsnbcpy_s, _mbsnbcpy_s_l

Копирует **n** байт строки в строку назначения. Это версии функций [_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t _mbsnbcpy_s(
   unsigned char * strDest,
   size_t sizeInBytes,
   const unsigned char * strSource,
   size_t count
);
errno_t _mbsnbcpy_s_l(
   unsigned char * strDest,
   size_t sizeInBytes,
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbcpy_s(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbcpy_s_l(
   unsigned char (&strDest)[size],
   const unsigned char * strSource,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Параметры

*strDest*<br/>
Место назначение для копирования строки символов.

*sizeInBytes*<br/>
Размер буфера назначения.

*strSource*<br/>
Копируемая строка символов.

*count*<br/>
Число байтов для копирования.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Ноль при успешном завершении; **EINVAL** Если был передан неправильный параметр.

## <a name="remarks"></a>Примечания

**_Mbsnbcpy_s** функции копии *число* байтов из *strSource* для *strDest*. Если *число* превышает размер *strDest*, либо входные строки является указателем null, или *sizeInBytes* или *число* равно 0, функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md) . Если выполнение может быть продолжено, функция возвращает **EINVAL**. Если строки источника и назначения перекрываются, то поведение **_mbsnbcpy_s** не определено.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

> [!NOTE]
> В отличие от версии небезопасные этой функции **_mbsnbcpy_s** не выполните null заполнения в строке, а значение всегда равно null завершает строку.

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncpy_s**|**_strncpy_s**|**_mbsnbcpy_s**|**_wcsncpy_s**|
|**_tcsncpy_s_l**|**_strncpy_s_l**|**_mbsnbcpy_s_l**|**_wcsncpy_s_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcpy_s**|\<mbstring.h>|
|**_mbsnbcpy_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
