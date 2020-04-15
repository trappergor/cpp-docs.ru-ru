---
title: getenv_s, _wgetenv_s
description: Описывает библиотеку getenv_s и _wgetenv_s функции выполнения Microsoft C.
ms.date: 4/2/2020
api_name:
- getenv_s
- _wgetenv_s
- _o__wgetenv_s
- _o_getenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- getenv_s
- _tgetenv_s
- _wgetenv_s
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
no-loc:
- getenv_s
- _wgetenv_s
- _putenv_s
- main
- wmain
- errno
- EINVAL
- ERANGE
- _environ
- _wenviron
- _putenv
- _wputenv
- _tgetenv_s
- _tzset
- _dupenv_s
- _wdupenv_s
ms.openlocfilehash: 17c4e001f7f4637f6f66f218c94378368976901f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344280"
---
# <a name="getenv_s-_wgetenv_s"></a>getenv_s, _wgetenv_s

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

*Буфера*<br/>
Буфер для хранения значения переменной среды.

*numberOfElements*<br/>
Размер *буфера*.

*варимя*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Ноль при успехе; код ошибки при неудаче.

### <a name="error-conditions"></a>Ситуации, которые могут привести к ошибке

|*pReturnValue*|*Буфера*|*numberOfElements*|*варимя*|Возвращаемое значение|
|--------------------|--------------|------------------------|---------------|------------------|
|**Null**|any|any|any|**EINVAL**|
|any|**Null**|> 0|any|**EINVAL**|
|any|any|any|**Null**|**EINVAL**|

При любом из этих условий ошибки вызывается обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение разрешено продолжать, функции, установленные **errno** **к EINVAL** и вернуть **EINVAL**.

Кроме того, если буфер слишком мал, эти функции возвращают **ERANGE.** Они не вызывают обработчик недопустимого параметра. Они выписывают необходимый размер буфера в *pReturnValue,* и тем самым позволяют программам снова вызывать функцию с большим буфером.

## <a name="remarks"></a>Remarks

Функция **getenv_s** выполняет поиск по списку переменных среды для *varname.* **getenv_s** не является чувствительным случаем в операционной системе Windows. **getenv_s** и [_putenv_s](putenv-s-wputenv-s.md) использовать копию среды, на которую указывает глобальная переменная **_environ** для доступа к окружающей среде. **getenv_s** работает только на структурах данных, доступных для библиотеки времени выполнения, а не на «сегменте» среды, созданном для процесса операционной системой. Таким образом, программы, которые используют аргумент *envp* для [основной](../../cpp/main-function-command-line-args.md) или [wmain](../../cpp/main-function-command-line-args.md) может получить недействительную информацию.

**_wgetenv_s** является широкохарактерным вариантом **getenv_s;** аргументивация и значение возврата **_wgetenv_s** являются широкохарактерными строками. **Глобальная** переменная _wenviron является широкохарактерной версией **_environ.**

В программе MBCS (например, в программе SBCS ASCII) **_wenviron** изначально **является NULL,** поскольку среда состоит из строк с мультибайт-символами. Затем, при первом вызове [_wputenv,](putenv-wputenv.md)или при первом вызове **_wgetenv_s,** если среда (MBCS) уже существует, создается соответствующая среда широкого характера строки, а затем указывается **на _wenviron.**

Аналогичным образом в программе Unicode **(_wmain)** **_environ** изначально **является NULL,** поскольку среда состоит из струн широкого характера. Затем, при первом вызове [_putenv,](putenv-wputenv.md)или при первом вызове **getenv_s** если среда (Unicode) уже существует, создается соответствующая среда MBCS, на которую указывает **_environ.**

Если две копии среды (многобайтовой кодировки и Юникода) существуют одновременно в программе, система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при вызове **_putenv,** вызов **_wputenv** также выполняется автоматически, чтобы две строки среды соответствовали.

> [!CAUTION]
> В редких случаях, когда система времени выполнения поддерживает как версию Юникода, так и многобайтовую версию среды, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная строка с многобайтовыми символами сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_putenv_s** и **_getenv_s** семейства функций не являются безопасными для потоков. **_getenv_s** может вернуть указатель строки, в то время как **_putenv_s** изменяет строку и тем самым вызывает случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

В C++ использование этих функций упрощено шаблонными перегрузками; перегрузки могут определить длину буфера автоматически, устранена необходимость указывать аргумент size. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

Для проверки или изменения значения переменной среды **ТЗ,** используйте **getenv_s,** **_putenv**и **_tzset,** по мере необходимости. Для получения дополнительной информации о **ТЗ,** см [_tzset](tzset.md) и [_daylight, _dstbias, _timezone и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[Экологические константы](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
