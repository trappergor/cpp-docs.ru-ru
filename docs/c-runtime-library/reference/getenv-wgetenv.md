---
title: getenv, _wgetenv | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- getenv
- _wgetenv
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
- _wgetenv
- getenv
- _tgetenv
dev_langs:
- C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2e68ca55d9e33995df583719e4797a6880d34ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="getenv-wgetenv"></a>getenv, _wgetenv

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

*varname*<br/>
Имя переменной среды.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на запись таблицы среды содержащий *varname*. Изменять значение переменной среды с помощью возвращенного указателя небезопасно. Используйте [_putenv](putenv-wputenv.md) функции для изменения значения переменной среды. Возвращает значение **NULL** Если *varname* не найден в таблице среды.

## <a name="remarks"></a>Примечания

**Getenv** функция выполняет поиск в списке переменных среды для *varname*. **getenv** регистр не учитывается в операционной системе Windows. **getenv** и **_putenv** используют копию среды, на который указывает глобальная переменная **_environ** для доступа к среде. **getenv** работает только в структурах данных, доступных в библиотеке времени выполнения, а не в среде «сегмент», созданном для процесса операционной системой. Поэтому программы, которые используют *envp* аргумент [основной](../../cpp/main-program-startup.md) или [wmain](../../cpp/main-program-startup.md) могут извлекать неверную информацию.

Если *varname* — **NULL**, эта функция вызывает обработчик недопустимого параметра, как описано в [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эта функция задает **errno** для **EINVAL** и возвращает **NULL**.

**_wgetenv** — это двухбайтовая версия **getenv**; аргумент и возвращаемое значение **_wgetenv** представляют собой строки расширенных символов. **_Wenviron** глобальная переменная — это двухбайтовая версия **_environ**.

В программе с многобайтовой Кодировкой (например, в программе однобайтовой Кодировкой ASCII) **_wenviron** изначально **NULL** поскольку среда состоит из строк многобайтовых символов. Затем на первый вызов [_wputenv](putenv-wputenv.md), или при первом вызове для **_wgetenv** Если среда (многобайтовой Кодировки) уже существует, создается соответствующая среда широкосимвольной строки и затем указывает **_wenviron**.

Аналогично в Юникоде (**_wmain**) программы, **_environ** изначально **NULL** поскольку среда состоит из строки расширенных символов. Затем на первый вызов **_putenv**, или при первом вызове для **getenv** Если среда (Юникода) уже существует, создается соответствующая среда многобайтовой Кодировки создается и затем указывает **_ Environ**.

Если в программе одновременно существуют две копии среды (многобайтовой кодировки и Юникода), система времени выполнения должна поддерживать обе копии, что отрицательно сказывается на скорости выполнения программы. Например, при каждом вызове **_putenv**, вызов **_wputenv** также выполняется автоматически, так что строки в двух средах совпадали.

> [!CAUTION]
> В редких случаях, когда система времени выполнения поддерживает и версию Юникода, и многобайтовую версию, эти две версии среды могут не полностью соответствовать друг другу. Это происходит потому, что хотя любая уникальная расширенная строка сопоставляется уникальной строке Юникода, сопоставление уникальной строки Юникода со строкой многобайтовой кодировки не обязательно будет уникальными. Дополнительные сведения см. в разделе [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> **_Putenv** и **_getenv** семейства функций не являются потокобезопасными. **_getenv** может вернуть указатель строки при **_putenv** изменяет строку, вызывая случайные сбои. Убедитесь, что вызовы этих функций синхронизированы.

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

Чтобы проверить или изменить значение **TZ** использование переменной среды **getenv**, **_putenv** и **_tzset** при необходимости. Дополнительные сведения о **TZ**, в разделе [_tzset](tzset.md) и [_daylight, timezone и _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> или \<wchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[Константы среды](../../c-runtime-library/environmental-constants.md)<br/>
