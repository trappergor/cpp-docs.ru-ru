---
title: _set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_invalid_parameter_handler
- _set_invalid_parameter_handler
- _set_thread_local_invalid_parameter_handler
dev_langs:
- C++
helpviewer_keywords:
- invalid parameter handler
- set_invalid_parameter_handler function
- _set_invalid_parameter_handler function
- _set_thread_local_invalid_parameter_handler function
ms.assetid: c0e67934-1a41-4016-ad8e-972828f3ac11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4808367c94ec6c869c7f3bcafd2965a317553a6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407607"
---
# <a name="setinvalidparameterhandler-setthreadlocalinvalidparameterhandler"></a>_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler

Устанавливает функцию для вызова, когда CRT обнаруживает недопустимый аргумент.

## <a name="syntax"></a>Синтаксис

```C
_invalid_parameter_handler _set_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
_invalid_parameter_handler _set_thread_local_invalid_parameter_handler(
   _invalid_parameter_handler pNew
);
```

### <a name="parameters"></a>Параметры

*pNew*<br/>
Указатель на функцию нового обработчика недопустимого параметра.

## <a name="return-value"></a>Возвращаемое значение

Указатель на обработчик недопустимого параметра до вызова.

## <a name="remarks"></a>Примечания

Многие функции времени выполнения C проверяют допустимость аргументов, передаваемых в них. Если передается недопустимый аргумент, функция может установить **errno** номер ошибки или вернуть код ошибки. В таких случаях также вызывается обработчик недопустимого параметра. Среда выполнения C предоставляет глобальный обработчик недопустимых параметров по умолчанию, который завершает программу и отображает сообщение об ошибке среды выполнения. Можно использовать **_set_invalid_parameter_handler** выполнить собственную функцию как обработчик глобального недопустимого параметра. Среда выполнения C также поддерживает локальный обработчик недопустимых параметров потока. Если обработчик параметра локального потока в поток задается с помощью **_set_thread_local_invalid_parameter_handler**, функции времени выполнения C, вызывается из потока используется этот обработчик вместо глобальный обработчик. Только одну функцию можно указать в качестве глобального обработчика недопустимых аргументов единовременно. Только одну функцию можно указать в качестве локального обработчика недопустимых аргументов для одного потока, но различные потоки могут иметь разные локальные обработчики потоков. Это позволяет изменять обработчик, который используется в одной части кода, не затрагивая работу других потоков.

Когда среда выполнения вызывает функцию обработки недопустимого параметра, это обычно означает, что возникла неисправимая ошибка. Указанная функция обработчика недопустимого параметра должна сохранить все данные, которые возможно сохранить, и затем прерваться. Она не должна возвращать управление функции main, если вы не уверены, что ошибка исправима.

Функция обработчика недопустимого параметра должна иметь следующий прототип:

```C
void _invalid_parameter(
   const wchar_t * expression,
   const wchar_t * function,
   const wchar_t * file,
   unsigned int line,
   uintptr_t pReserved
);
```

*Выражение* аргумента представлена в виде двухбайтового строкового выражения аргумента, вызвавшего ошибку. *Функция* аргумент — имя функции CRT, которая получила недопустимый аргумент. *Файл* аргумент является именем CRT исходного файла, содержащего функцию. *Строки* аргумент — это номер строки в этом файле. Последний аргумент зарезервирован. Все параметры имеют значение **NULL** Если не используется отладочная версия библиотеки CRT.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_invalid_parameter_handler**, **_set_thread_local_invalid_parameter_handler**|C: \<stdlib.h><br /><br /> C++: \<cstdlib> или \<stdlib.h>|

**_Set_invalid_parameter_handler** и **_set_thread_local_invalid_parameter_handler** функции — только к системам Майкрософт. Сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

В следующем примере обработчик ошибок недопустимого параметра используется для печати функции, которая получила недопустимый параметр, и файла и строки в источниках CRT. Если используется отладочная библиотека CRT, ошибки недопустимого параметра также создают утверждение, которое отключено в этом примере с помощью [_CrtSetReportMode](crtsetreportmode.md).

```C
// crt_set_invalid_parameter_handler.c
// compile with: /Zi /MTd
#include <stdio.h>
#include <stdlib.h>
#include <crtdbg.h>  // For _CrtSetReportMode

void myInvalidParameterHandler(const wchar_t* expression,
   const wchar_t* function,
   const wchar_t* file,
   unsigned int line,
   uintptr_t pReserved)
{
   wprintf(L"Invalid parameter detected in function %s."
            L" File: %s Line: %d\n", function, file, line);
   wprintf(L"Expression: %s\n", expression);
   abort();
}

int main( )
{
   char* formatString;

   _invalid_parameter_handler oldHandler, newHandler;
   newHandler = myInvalidParameterHandler;
   oldHandler = _set_invalid_parameter_handler(newHandler);

   // Disable the message box for assertions.
   _CrtSetReportMode(_CRT_ASSERT, 0);

   // Call printf_s with invalid parameters.

   formatString = NULL;
   printf(formatString);
}
```

```Output
Invalid parameter detected in function common_vfprintf. File: minkernel\crts\ucrt\src\appcrt\stdio\output.cpp Line: 32
Expression: format != nullptr
```

## <a name="see-also"></a>См. также

[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[Версии функций CRT повышенной безопасности](../../c-runtime-library/security-enhanced-versions-of-crt-functions.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
