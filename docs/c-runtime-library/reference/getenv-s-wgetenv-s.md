---
title: getenv_s, _wgetenv_s | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- getenv_s
- _wgetenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- getenv_s
- _tgetenv_s
- _wgetenv_s
dev_langs:
- C++
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
caps.latest.revision: 42
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21f0877f2b82f243603dc7fb4edf3eff2bbf4d89
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="getenvs-wgetenvs"></a>getenv_s, _wgetenv_s

Получает значение из текущей среды. Это версии функций [getenv, _wgetenv](getenv-wgetenv.md) с повышенной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
errno_t getenv_s(
   size_t *pReturnValue,
   char* buffer,
   size_t numberOfElements,
   const char *varname
);
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *varname
);
template <size_t size>
errno_t getenv_s(
   size_t *pReturnValue,
   char (&buffer)[size],
   const char *varname
); // C++ only
template <size_t size>
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t (&buffer)[size],
   const wchar_t *varname
); // C++ only
```

### <a name="parameters"></a>Параметры

*pReturnValue*<br/>
Требуемый размер буфера или 0, если переменная не найдена.

*buffer*<br/>
Буфер для хранения значения переменной среды.

*numberOfElements*<br/>
Размер *буфера*.

*varname*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Ноль при успехе; код ошибки при неудаче.

### <a name="error-conditions"></a>Условия ошибок

|*pReturnValue*|*buffer*|*numberOfElements*|*varname*|Возвращаемое значение|
|--------------------|--------------|------------------------|---------------|------------------|
|**NULL**|any|any|any|**EINVAL**|
|any|**NULL**|>0|any|**EINVAL**|
|any|any|any|**NULL**|**EINVAL**|

При любом из этих условий ошибки вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, функции задают **errno** для **EINVAL** и возвращают **EINVAL**.

Кроме того, если буфер слишком мал, эти функции возвращают **ERANGE**. Они не вызывают обработчик недопустимого параметра. Они записывают необходимый размер буфера в *pReturnValue*и тем самым включить программы могут вызвать функцию снова с большим буфером.

## <a name="remarks"></a>Примечания

**Getenv_s** функция выполняет поиск в списке переменных среды для *varname*. **getenv_s** регистр не учитывается в операционной системе Windows. **getenv_s** и [_putenv_s](putenv-s-wputenv-s.md) используют копию среды, на который указывает глобальная переменная **_environ** для доступа к среде. **getenv_s** работает только в структурах данных, доступных в библиотеке времени выполнения, а не в «сегменте» среды, созданном для процесса операционной системой. Поэтому программы, которые используют *envp* аргумент [основной](../../cpp/main-program-startup.md) или [wmain](../../cpp/main-program-startup.md) могут извлекать неверную информацию.

**_wgetenv_s** — это двухбайтовая версия **getenv_s**; аргумент и возвращаемое значение **_wgetenv_s** представляют собой строки расширенных символов. **_Wenviron** глобальная переменная — это двухбайтовая версия **_environ**.

В программе с многобайтовой Кодировкой (например, в программе однобайтовой Кодировкой ASCII) **_wenviron** изначально **NULL** поскольку среда состоит из строк многобайтовых символов. Затем на первый вызов [_wputenv](putenv-wputenv.md), или при первом вызове для **_wgetenv_s**, если среда (многобайтовой Кодировки) уже существует, создается соответствующая среда широкосимвольной строки, создается и затем указывает **_wenviron**.

Аналогично в Юникоде (**_wmain**) программы, **_environ** изначально **NULL** поскольку среда состоит из строки расширенных символов. Затем на первый вызов [_putenv](putenv-wputenv.md), или при первом вызове для **getenv_s** Если среда (Юникода) уже существует, создается соответствующая среда многобайтовой Кодировки создается и затем указывает **_ Environ**.

Если две копии среды (многобайтовой кодировки и Юникода) существуют одновременно в программе, система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при вызове **_putenv**, вызов **_wputenv** также выполняется автоматически, чтобы строки в двух средах совпадали.

> [!CAUTION]
> В редких случаях, когда система времени выполнения поддерживает как версию Юникода, так и многобайтовую версию среды, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная строка с многобайтовыми символами сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv_s** и **_getenv_s** семейства функций не являются потокобезопасными. **_getenv_s** может вернуть указатель строки при **_putenv_s** изменяет строку, что может вызвать случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

Чтобы проверить или изменить значение **TZ** использование переменной среды **getenv_s**, **_putenv**, и **_tzset**в соответствии с требованием. Дополнительные сведения о **TZ**, в разделе [_tzset](tzset.md) и [_daylight, _dstbias, _timezone и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getenv_s.c
// This program uses getenv_s to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* libvar;
   size_t requiredSize;

   getenv_s( &requiredSize, NULL, 0, "LIB");
   if (requiredSize == 0)
   {
      printf("LIB doesn't exist!\n");
      exit(1);
   }

   libvar = (char*) malloc(requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects
   // the environment variable of the current process. The command
   // processor's environment is not changed.
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );

   getenv_s( &requiredSize, NULL, 0, "LIB");

   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the new value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "New LIB variable is: %s\n", libvar );

   free(libvar);
}
```

```Output
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
