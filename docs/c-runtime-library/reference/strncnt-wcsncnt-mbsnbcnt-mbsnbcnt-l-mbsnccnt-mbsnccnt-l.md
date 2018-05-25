---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
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
- _mbsnbcnt
- wcsncnt
- _tcsnbcnt
- _mbsnccnt
- _ftcsnbcnt
- mbsnbcnt
- strncnt
- mbsnbcnt_l
- mbsnccnt_l
- mbsnccnt
- _strncnt
- _wcsncnt
dev_langs:
- C++
helpviewer_keywords:
- _strncnt function
- _mbsnbcnt function
- _mbsnbcnt_l function
- _mbsnccnt_l function
- mbsnbcnt_l function
- mbsnbcnt function
- tcsnbcnt function
- mbsnccnt_l function
- strncnt function
- _tcsnbcnt function
- mbsnccnt function
- wcsncnt function
- _mbsnccnt function
- _wcsncnt function
ms.assetid: 2a022e9e-a307-4acb-a66b-e56e5357f848
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 066431205ecd7aa2b193350ccda4a83decac0458
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
---
# <a name="strncnt-wcsncnt-mbsnbcnt-mbsnbcntl-mbsnccnt-mbsnccntl"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

Возвращает число символов или байтов в пределах указанного количества.

> [!IMPORTANT]
> **_mbsnbcnt**, **_mbsnbcnt_l**, **_mbsnccnt**, и **_mbsnccnt_l** не может использоваться в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
size_t _strncnt(
   const char *str,
   size_t count
);
size_t _wcsncnt(
   const wchar_t *str,
   size_t count
);
size_t _mbsnbcnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnbcnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
size_t _mbsnccnt(
   const unsigned char *str,
   size_t count
);
size_t _mbsnccnt_l(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);

```

### <a name="parameters"></a>Параметры

*str*<br/>
Строка, которую необходимо проверить.

*count*<br/>
Число символов или байтов, которые необходимо проанализировать в *str*.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbsnbcnt** и **_mbsnbcnt_l** возвращают число байтов найден в первом *число* многобайтовых символов из *str*. **_mbsnccnt** и **_mbsnccnt_l** возвращают количество символов, найден в первом *число* байтов *str*. Если обнаружен символ null перед изменением *str* имеет завершена, они возвращают число байт или символов, найдены перед символом null. Если *str* состоит из не более чем *число* символов или байтов, они возвращают число символов или байтов в строку. Если *число* меньше нуля, они возвращают 0. В предыдущих версиях эти функции было возвращаемым значением типа **int** вместо **size_t**.

**_strncnt** возвращает число знаков в первом *число* байт строки однобайтовых *str*. **_wcsncnt** возвращает число знаков в первом *число* расширенных символов строки расширенных символов *str*.

## <a name="remarks"></a>Примечания

**_mbsnbcnt** и **_mbsnbcnt_l** определения числа байтов найден в первом *число* многобайтовых символов из *str*. **_mbsnbcnt** и **_mbsnbcnt_l** заменить **mtob** и должны использоваться вместо **mtob**.

**_mbsnccnt** и **_mbsnccnt_l** число символы, входящие в первом *число* байтов *str*. Если **_mbsnccnt** и **_mbsnccnt_l** возникает нуль-символ во второй байт двухбайтовых символов, первый байт также считается должен иметь значение null и не включается в возвращаемое значение. **_mbsnccnt** и **_mbsnccnt_l** заменить **btom** и должны использоваться вместо **btom**.

Если *str* — **NULL** указатель или *число* равно 0, эти функции вызывают обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md), **errno** равно **EINVAL**, и функция возвращает значение 0.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|Н/Д|
|**_wcsncnt**|Н/Д|Н/Д|**_mbsnbcnt**|
|**_wcsncnt**|Н/Д|Н/Д|**_mbsnccnt**|
|Н/Д|Н/Д|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_mbsnbcnt.c

#include  <mbstring.h>
#include  <stdio.h>

int main( void )
{
   unsigned char str[] = "This is a multibyte-character string.";
   unsigned int char_count, byte_count;
   char_count = _mbsnccnt( str, 10 );
   byte_count = _mbsnbcnt( str, 10 );
   if ( byte_count - char_count )
      printf( "The first 10 characters contain %d multibyte characters\n", char_count );
   else
      printf( "The first 10 characters are single-byte.\n");
}
```

### <a name="output"></a>Вывод

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
