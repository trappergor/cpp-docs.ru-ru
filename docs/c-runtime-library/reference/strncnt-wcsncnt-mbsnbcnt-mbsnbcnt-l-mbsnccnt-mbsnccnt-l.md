---
title: _strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l
ms.date: 4/2/2020
api_name:
- _mbsnbcnt_l
- _mbsnccnt
- _wcsncnt
- _strncnt
- _mbsnccnt_l
- _mbsnbcnt
- _o__mbsnbcnt
- _o__mbsnbcnt_l
- _o__mbsnccnt
- _o__mbsnccnt_l
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
ms.openlocfilehash: bfd339a38dd5df30ece72059525860603ee10748
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364183"
---
# <a name="_strncnt-_wcsncnt-_mbsnbcnt-_mbsnbcnt_l-_mbsnccnt-_mbsnccnt_l"></a>_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l

Возвращает число символов или байтов в пределах указанного количества.

> [!IMPORTANT]
> **_mbsnbcnt,** **_mbsnbcnt_l,** **_mbsnccnt**и **_mbsnccnt_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Ул*<br/>
Строка, которую необходимо проверить.

*count*<br/>
Количество символов или байтов, которые будут рассмотрены в *str*.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_mbsnbcnt** и **_mbsnbcnt_l** вернуть количество байтов, найденных в первом *подсчете* мультибайтных символов *str.* **_mbsnccnt** и **_mbsnccnt_l** вернуть количество символов, найденных в первом *отсчете* байтов *str.* Если нулевой символ встречается до завершения экспертизы *str,* они возвращают количество байтов или символов, найденных до нулевого символа. Если *str* состоит из менее чем *кол символов* или байтов, они возвращают количество символов или байтов в строке. Если *количество* меньше нуля, они возвращают 0. В предыдущих версиях эти функции имели значение возврата типа **int,** а не **size_t.**

**_strncnt** возвращает количество символов в первом *счету* байтов однобайной строки *str*. **_wcsncnt** возвращает количество символов в первом *отсчете* широких символов широкой *строки*str.

## <a name="remarks"></a>Remarks

**_mbsnbcnt** и **_mbsnbcnt_l** подсчитывать количество байтов, найденных в первом *подсчете* мультибайтных символов *str.* **_mbsnbcnt** и **_mbsnbcnt_l** заменить **mtob** и должны использоваться вместо **mtob**.

**_mbsnccnt** и **_mbsnccnt_l** подсчитывают количество символов, найденных в первом *подсчете* байтов *str.* Если **_mbsnccnt** и **_mbsnccnt_l** сталкиваются с нулевым персонажем во втором байте двойного байт-персонажа, первый байт также считается недействительным и не входит в возвращенное значение подсчета. **_mbsnccnt** и **_mbsnccnt_l** заменить **бтом** и должны использоваться вместо **бтома.**

Если *str* является указателем **NULL** или *составляет* 0, эти функции вызывают недействительный обработчик параметров, как описано в [проверке параметра,](../../c-runtime-library/parameter-validation.md) **errno** устанавливается на **EINVAL,** и функция возвращает 0.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|-------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnbcnt**|**_strncnt**|**_mbsnbcnt**|**_wcsncnt**|
|**_tcsnccnt**|**_strncnt**|**_mbsnbcnt**|Недоступно|
|**_wcsncnt**|Недоступно|Недоступно|**_mbsnbcnt**|
|**_wcsncnt**|Недоступно|Недоступно|**_mbsnccnt**|
|Недоступно|Недоступно|**_mbsnbcnt_l**|**_mbsnccnt_l**|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcnt**|\<mbstring.h>|
|**_mbsnbcnt_l**|\<mbstring.h>|
|**_mbsnccnt**|\<mbstring.h>|
|**_mbsnccnt_l**|\<mbstring.h>|
|**_strncnt**|\<tchar.h>|
|**_wcsncnt**|\<tchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

### <a name="output"></a>Выходные данные

```Output
The first 10 characters are single-byte.
```

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
