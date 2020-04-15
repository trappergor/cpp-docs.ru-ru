---
title: getenv, _wgetenv
description: Описывает библиотеку getenv и _wgetenv функции выполнения Microsoft C.
ms.date: 4/2/2020
api_name:
- getenv
- _wgetenv
- _o__wgetenv
- _o_getenv
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
- _wgetenv
- getenv
- _tgetenv
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
no-loc:
- getenv
- _wgetenv
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
ms.openlocfilehash: c9d7f7e1a2c5d6b15aee2f7f972a30cc0c90115c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344252"
---
# <a name="getenv-_wgetenv"></a>getenv, _wgetenv

Получает значение из текущей среды. Существуют более безопасные версии этих функций; см. раздел [getenv_s, _wgetenv_s](getenv-s-wgetenv-s.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>Параметры

*варимя*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на вход таблицы среды, содержащий *varname.* Изменять значение переменной среды с помощью возвращенного указателя небезопасно. Используйте [функцию _putenv](putenv-wputenv.md) для изменения значения переменной среды. Значение возврата **NULL,** если *varname* не найдено в таблице среды.

## <a name="remarks"></a>Remarks

Функция **getenv** выполняет поиск по списку переменных среды для *varname.* **getenv** не является чувствительным случаем в операционной системе Windows. **getenv** и **_putenv** использовать копию окружающей среды, на которую указывает глобальная переменная **_environ** для доступа к окружающей среде. **getenv** работает только на структурах данных, доступных для библиотеки времени выполнения, а не на «сегменте» среды, созданном для процесса операционной системой. Таким образом, программы, которые используют *аргумент envp* для [основной](../../cpp/main-function-command-line-args.md) или [wmain](../../cpp/main-function-command-line-args.md) может получить недействительную информацию.

Если *varname* **null,** эта функция вызывает недействительный обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция устанавливает **errno** **к EINVAL** и возвращает **NULL**.

**_wgetenv** является широкохарактерным вариантом **getenv;** аргументивация и значение возврата **_wgetenv** являются широкохарактерными строками. **Глобальная** переменная _wenviron является широкохарактерной версией **_environ.**

В программе MBCS (например, в программе SBCS ASCII) **_wenviron** изначально **является NULL,** поскольку среда состоит из строк с мультибайт-символами. Затем, при первом вызове [_wputenv,](putenv-wputenv.md)или при первом вызове **_wgetenv** если среда (MBCS) уже существует, создается соответствующая среда строк широкого характера, на которую указывает **_wenviron.**

Аналогичным образом в программе Unicode **(_wmain)** **_environ** изначально **является NULL,** поскольку среда состоит из струн широкого характера. Затем, при первом вызове **_putenv,** или при первом вызове **getenv,** если (Unicode) среда уже существует, создается соответствующая среда MBCS, а затем указывается **на _environ.**

Если в программе одновременно существуют две копии среды (многобайтовой кодировки и Юникода), система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, всякий раз, когда вы звоните **_putenv,** вызов **_wputenv** также выполняется автоматически, так что две строки среды соответствуют.

> [!CAUTION]
> В редких случаях, когда система времени выполнения поддерживает и версию Юникода, и многобайтовую версию, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная расширенная строка сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_putenv** и **_getenv** семейства функций не являются безопасными для потоков. **_getenv** может вернуть указатель строки, в то время как **_putenv** изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

Для проверки или изменения значения переменной среды **ТЗ** используйте **getenv,** **_putenv** и **_tzset** по мере необходимости. Для получения дополнительной информации о **ТЗ,** см [_tzset](tzset.md) и [_daylight, часовой пояс и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_getenv.c
// compile with: /W3
// This program uses getenv to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *libvar;

   // Get the value of the LIB environment variable.
   libvar = getenv( "LIB" ); // C4996
   // Note: getenv is deprecated; consider using getenv_s instead

   if( libvar != NULL )
      printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects the environment
   // variable of the current process. The command processor's
   // environment is not changed.
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996
   // Note: _putenv is deprecated; consider using putenv_s instead

   // Get new value.
   libvar = getenv( "LIB" ); // C4996

   if( libvar != NULL )
      printf( "New LIB variable is: %s\n", libvar );
}
```

```Output
Original LIB variable is: C:\progra~1\devstu~1\vc\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>См. также раздел

[Контроль процесса и окружающей среды](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
