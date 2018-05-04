---
title: _invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b0fecd7eefe9ac6a7a479fb12475b2b1c769cf4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

*выражение* строку, представляющую выражение параметра исходного кода, является недопустимым.

*имя_функции* имя функции, вызывается обработчик.

*имя_файла* файл исходного кода, в которой был вызван обработчик.

*номер_строки* номер строки в исходном коде, в которой был вызван обработчик.

*зарезервированные* не используется.

## <a name="return-value"></a>Возвращаемое значение

Эти функции не возвращают значения. **_Invalid_parameter_noinfo_noreturn** и **_invoke_watson** функции не возвращать вызывающему объекту, а в некоторых случаях **_invalid_parameter** и **_invalid_parameter_noinfo** могут не возвращать вызывающему объекту.

## <a name="remarks"></a>Примечания

Если функциям библиотеки времени выполнения C передаются недопустимые параметры, они вызывают *обработчик недопустимого параметра*. Он представляет собой функцию, в которой программист задает выполнение определенных действий. Например, обработчик может сообщить о проблеме пользователю, записать данные в журнал, установить прерывание в отладчике, завершить работу программы или не выполнять никаких действий. Если ни одна из функций, заданные программиста, обработчик по умолчанию **_invoke_watson**, вызывается.

По умолчанию, когда недопустимого параметра определяется в код отладки функции библиотеки CRT вызывать функцию **_invalid_parameter** использование подробных параметров. В коде неотладочные **_invalid_parameter_noinfo** вызывается функция, который вызывает **_invalid_parameter** функцию при помощи пустой параметров. Если функции библиотеки CRT неотладочные требуется завершение программы **_invalid_parameter_noinfo_noreturn** вызывается функция, который вызывает **_invalid_parameter** функцию при помощи пустой параметры, а затем путем вызова **_invoke_watson** функция принудительное завершение программы.

**_Invalid_parameter** функция проверяет ли был задан обработчик недопустимого параметра, определяемого пользователем и если да, вызывает ее. Например, если в текущем потоке пользователь определил локальный для потока обработчик, вызвав функцию [set_thread_local_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. Если пользователь определил глобальный обработчик недопустимого параметра, вызвав функцию [set_invalid_parameter_handler](set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. В противном случае обработчик по умолчанию **_invoke_watson** вызывается. Поведение по умолчанию **_invoke_watson** состоит в завершении программы. Определенные пользователем обработчики могут завершать работу программы или выполнять возврат. В тех случаях, когда восстановление работоспособности программы не гарантировано, рекомендуется завершать ее.

Когда обработчик по умолчанию **_invoke_watson** вызывается, если обработчик поддерживает [__fastfail](../../intrinsics/fastfail.md) операции, он вызывается при помощи параметра **FAST_FAIL_INVALID_ARG** и процесс завершается. В противном случае возникает исключение с быстрым прекращением, которое может быть перехвачено с помощью связанного отладчика. Если процесс может быть продолжено, она прекращается вызовом Windows **TerminateProcess** функцию при помощи состояние кода исключения **STATUS_INVALID_CRUNTIME_PARAMETER**.

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
