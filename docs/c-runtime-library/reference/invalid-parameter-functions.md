---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
ms.date: 11/04/2016
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation:
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: e43d5caaeebb6303d209d870c804357117812985
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157543"
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson

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

*Выражение*<br/>
Строка, представляющая выражение параметра исходного кода, которое не является допустимым.

*имя функции*<br/>
Имя функции, которая вызвала обработчик.

*file_name*<br/>
Файл исходного кода, в котором был вызван обработчик.

*line_number*<br/>
Номер строки в исходном коде, где был вызван обработчик.

*Зарезервировано*<br/>
Не используется.

## <a name="return-value"></a>Возвращаемое значение

Эти функции не возвращают значения. **_Invalid_parameter_noinfo_noreturn** и **_invoke_watson** функции не возвращают вызывающей стороне, а также в некоторых случаях **_invalid_parameter** и **_invalid_parameter_noinfo** могут не возвращать вызывающему объекту.

## <a name="remarks"></a>Примечания

Если функциям библиотеки времени выполнения C передаются недопустимые параметры, они вызывают *обработчик недопустимого параметра*. Он представляет собой функцию, в которой программист задает выполнение определенных действий. Например, обработчик может сообщить о проблеме пользователю, записать данные в журнал, установить прерывание в отладчике, завершить работу программы или не выполнять никаких действий. Если не указал никакую функцию программистом, обработчик по умолчанию **_invoke_watson**, вызывается.

По умолчанию, после которого недопустимый параметр в коде отладки функции библиотеки CRT вызвать функцию **_invalid_parameter** с подробными параметрами. В обычном коде **_invalid_parameter_noinfo** вызывается функция, которая вызывает **_invalid_parameter** работать с пустыми параметрами. Если функции библиотеки CRT без отладки необходимо завершить работу программы, **_invalid_parameter_noinfo_noreturn** вызывается функция, которая вызывает **_invalid_parameter** функционировать с использованием пустой параметры, а затем с помощью вызова **_invoke_watson** функции для принудительного завершения программы.

**_Invalid_parameter** функция проверки ли обработчик недопустимого параметра, определенного пользователя было установлено и если да, вызывает его. Например, если в текущем потоке пользователь определил локальный для потока обработчик, вызвав функцию [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. Если пользователь определил глобальный обработчик недопустимого параметра, вызвав функцию [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. В противном случае обработчик по умолчанию **_invoke_watson** вызывается. По умолчанию **_invoke_watson** завершает программу. Определенные пользователем обработчики могут завершать работу программы или выполнять возврат. В тех случаях, когда восстановление работоспособности программы не гарантировано, рекомендуется завершать ее.

Когда обработчик по умолчанию **_invoke_watson** вызывается, если процессор поддерживает [__fastfail](../../intrinsics/fastfail.md) операции, он вызывается с параметром **FAST_FAIL_INVALID_ARG** и процесс завершается. В противном случае возникает исключение с быстрым прекращением, которое может быть перехвачено с помощью связанного отладчика. Если процесс может быть продолжено, она прекращается вызовом Windows **TerminateProcess** функционировать с использованием состояния кода исключения из **STATUS_INVALID_CRUNTIME_PARAMETER**.

## <a name="requirements"></a>Требования

|Функция|Обязательный заголовок|
|--------------|------------------|
|**_invalid_parameter**, **_invalid_parameter_noinfo**, **_invalid_parameter_noinfo_noreturn**, **_invoke_watson**|\<corecrt.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](crt-alphabetical-function-reference.md)<br/>
[_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)<br/>
[_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)<br/>
[Проверка параметров](../../c-runtime-library/parameter-validation.md)<br/>
