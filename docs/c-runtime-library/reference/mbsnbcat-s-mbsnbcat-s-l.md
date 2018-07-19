---
title: _mbsnbcat_s, _mbsnbcat_s_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbcat_s_l
- _mbsnbcat_s
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
- _mbsnbcat_s
- mbsnbcat_s
- _mbsnbcat_s_l
- mbsnbcat_s_l
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cead47b21a066d7e55c22d6bc8fba63cb73a0224
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405118"
---
# <a name="mbsnbcats-mbsnbcatsl"></a>_mbsnbcat_s, _mbsnbcat_s_l

Добавляет строку многобайтовых символов не больше первого **n** байт другой многобайтовой строки. Это версии функций [_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

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

*sizeInBytes*<br/>
Размер *dest* буфера в байтах.

*src*<br/>
Исходная многобайтовая строка, завершаемая нуль-символом.

*count*<br/>
Число байтов из *src* для добавления *dest*.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Ноль в случае успешного выполнения; в противном случае — код ошибки.

### <a name="error-conditions"></a>Условия ошибок

|**dest**|*sizeInBytes*|*src*|Возвращаемое значение|
|------------|-------------------|-----------|------------------|
|**NULL**|any|any|**EINVAL**|
|Любой|<= 0|any|**EINVAL**|
|Любой|any|**NULL**|**EINVAL**|

Если возникает какое-либо из условий ошибки, функция создает ошибку недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если ошибка обработана, функция возвращает **EINVAL** и задает **errno** для **EINVAL**.

## <a name="remarks"></a>Примечания

**_Mbsnbcat_s** добавляет функцию *dest*, не более первый *число* байт *src*. Если байт непосредственно перед нуль-символ в *dest* является старшим байтом, он перезаписывается начальный байт строки *src*. В противном случае начальный байт строки *src* перезаписывает завершающий нуль-символ из *dest*. Если байт null встречается в *src* перед *число* добавлены байты, **_mbsnbcat_s** добавляет все байты из *src*, вплоть до null символ. Если *число* больше, чем длина *src*, длина *src* используется вместо *число*. Результирующая строка завершается нуль-символом. Если копирование производится между перекрывающимися строками, поведение не определено.

Выходное значение зависит от настройки **LC_CTYPE** категории языкового стандарта см. в разделе [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. Версии этих функций идентичны, за исключением тех, которые не имеют **_l** суффикс используют текущий языковой стандарт и те, которые имеют **_l** суффикс вместо этого используйте параметр языкового стандарта с Переданный. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные функции могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).

Отладочные версии этих функций сначала заполняют буфер значением 0xFD. Чтобы отключить это поведение, используйте [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat_s**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_s_l**|**_strncat_s_l**|**_mbsnbcat_s_l**|**_wcsncat_s_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcat_s**|\<mbstring.h>|
|**_mbsnbcat_s_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbcpy_s, _mbsnbcpy_s_l](mbsnbcpy-s-mbsnbcpy-s-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)<br/>
