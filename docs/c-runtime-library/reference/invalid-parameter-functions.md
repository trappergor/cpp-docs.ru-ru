---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
ms.date: 4/2/2020
api_name:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
- _o__invalid_parameter_noinfo
- _o__invalid_parameter_noinfo_noreturn
api_location:
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CORECRT/_invalid_parameter
- _invalid_parameter
- CORECRT/_invalid_parameter_noinfo
- _invalid_parameter_noinfo
- CORECRT/_invalid_parameter_noinfo_noreturn
- _invalid_parameter_noinfo_noreturn
- CORECRT/_invoke_watson
- _invoke_watson
ms.assetid: a4d6f1fd-ce56-4783-8719-927151a7a814
ms.openlocfilehash: 0f0a3ea3e1f2e43d53650b4017905c696269ce20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343947"
---
# <a name="_invalid_parameter-_invalid_parameter_noinfo-_invalid_parameter_noinfo_noreturn-_invoke_watson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

Эти функции используются библиотекой времени выполнения C для обработки недопустимых параметров, передаваемых в функции библиотеки CRT. Эти функции также могут использоваться в коде для поддержки определенных по умолчанию или настраиваемых механизмов обработки недопустимых параметров.

## <a name="syntax"></a>Синтаксис

```C
extern "C" void __cdecl
_invalid_parameter(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);

extern "C" void __cdecl
_invalid_parameter_noinfo(void);

extern "C" __declspec(noreturn) void __cdecl
_invalid_parameter_noinfo_noreturn(void);

extern "C" __declspec(noreturn) void __cdecl
_invoke_watson(
    wchar_t const* const expression,
    wchar_t const* const function_name,
    wchar_t const* const file_name,
    unsigned int   const line_number,
    uintptr_t      const reserved);
```

## <a name="parameters"></a>Параметры

*выражение*<br/>
Строка, представляющая выражение параметра исходного кода, которое не является допустимым.

*function_name*<br/>
Имя функции, которая вызвала обработчик.

*file_name*<br/>
Файл исходного кода, в котором был вызван обработчик.

*line_number*<br/>
Номер строки в исходном коде, где был вызван обработчик.

*Защищены*<br/>
Не используется.

## <a name="return-value"></a>Возвращаемое значение

Эти функции не возвращают значения. **функции _invalid_parameter_noinfo_noreturn** и **_invoke_watson** не возвращаются вызывающему абоненту, а в некоторых случаях **_invalid_parameter** и **_invalid_parameter_noinfo** не могут вернуться к вызывающему абоненту.

## <a name="remarks"></a>Remarks

Если функциям библиотеки времени выполнения C передаются недопустимые параметры, они вызывают *обработчик недопустимого параметра*. Он представляет собой функцию, в которой программист задает выполнение определенных действий. Например, обработчик может сообщить о проблеме пользователю, записать данные в журнал, установить прерывание в отладчике, завершить работу программы или не выполнять никаких действий. Если ни одна функция не указана программистом, вызывается обработчик по умолчанию, **_invoke_watson.**

По умолчанию, когда недействительный параметр идентифицируется в коде отладки, функции библиотеки CRT вызывают функцию **_invalid_parameter** используя многословные параметры. В коде без отливки вызывается **функция _invalid_parameter_noinfo,** которая вызывает **функцию _invalid_parameter** с помощью пустых параметров. Если функция библиотеки неотлиповки CRT требует завершения программы, вызывается **функция _invalid_parameter_noinfo_noreturn,** которая вызывает **функцию _invalid_parameter** с помощью пустых параметров, а затем вызывает сявок в **функцию _invoke_watson,** чтобы заставить окончание программы.

**Функция _invalid_parameter** проверяет, был ли установлен определенный пользователем недействительный обработчик параметров, и если да, то вызывает его. Например, если в текущем потоке пользователь определил локальный для потока обработчик, вызвав функцию [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. Если пользователь определил глобальный обработчик недопустимого параметра, вызвав функцию [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. В противном случае вызывается **_invoke_watson** обработчика по умолчанию. Поведение **_invoke_watson** по умолчанию заключается в прекращении программы. Определенные пользователем обработчики могут завершать работу программы или выполнять возврат. В тех случаях, когда восстановление работоспособности программы не гарантировано, рекомендуется завершать ее.

При вызове обработчика по умолчанию **_invoke_watson,** если процессор поддерживает [__fastfail](../../intrinsics/fastfail.md) операцию, он вызывается с помощью параметра **FAST_FAIL_INVALID_ARG** и процесс завершается. В противном случае возникает исключение с быстрым прекращением, которое может быть перехвачено с помощью связанного отладчика. Если процесс разрешен к продолжению, он завершается вызовом в функцию Windows **TerminateProcess** с использованием статуса кода исключения **STATUS_INVALID_CRUNTIME_PARAMETER.**

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Компонент|Обязательный заголовок|
|--------------|------------------|
|**_invalid_parameter,** **_invalid_parameter_noinfo,** **_invalid_parameter_noinfo_noreturn,** **_invoke_watson**|\<corecrt.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Проверка параметров](../../c-runtime-library/parameter-validation.md)<br/>
