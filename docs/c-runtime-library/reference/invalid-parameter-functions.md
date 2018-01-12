---
title: "_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _invalid_parameter
- _invalid_parameter_noinfo
- _invalid_parameter_noinfo_noreturn
- _invoke_watson
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
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
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4db706387387d00d754f2afe74e34e85aecc5199
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="invalidparameter-invalidparameternoinfo-invalidparameternoinfonoreturn-invokewatson"></a>_invalid_parameter, _invalid_parameter_noinfo, _invalid_parameter_noinfo_noreturn, _invoke_watson
Эти функции используются библиотекой времени выполнения C для обработки недопустимых параметров, передаваемых в функции библиотеки CRT. Эти функции также могут использоваться в коде для поддержки определенных по умолчанию или настраиваемых механизмов обработки недопустимых параметров.

## <a name="syntax"></a>Синтаксис
```
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

## <a name="return-value"></a>Возвращаемое значение
Эти функции не возвращают значения. Функции `_invalid_parameter_noinfo_noreturn` и `_invoke_watson` не возвращают данные вызывающему объекту. В некоторых случаях аналогичным образом ведут себя функции `_invalid_parameter` и `_invalid_parameter_noinfo`.

## <a name="parameters"></a>Параметры
`expression`  
Строка, представляющая выражение параметра исходного кода, которое не является допустимым.

`function_name`  
Имя функции, которая вызвала обработчик.

`file_name`  
Файл исходного кода, в котором был вызван обработчик.

`line_number`  
Номер строки в исходном коде, где был вызван обработчик.

`reserved`  
Не используется.

## <a name="remarks"></a>Примечания
Если функциям библиотеки времени выполнения C передаются недопустимые параметры, они вызывают *обработчик недопустимого параметра*. Он представляет собой функцию, в которой программист задает выполнение определенных действий. Например, обработчик может сообщить о проблеме пользователю, записать данные в журнал, установить прерывание в отладчике, завершить работу программы или не выполнять никаких действий. Если программист не указал никакую функцию, по умолчанию вызывается обработчик `_invoke_watson`.

Если в коде отладки обнаруживается недопустимый параметр, функции библиотеки CRT по умолчанию вызывают функцию `_invalid_parameter` с подробными параметрами. В обычном коде вызывается функция `_invalid_parameter_noinfo`, которая, в свою очередь, вызывает функцию `_invalid_parameter` с пустыми параметрами. Если функции библиотеки CRT, не осуществляющей отладку, требуется завершить работу программы, вызывается функция `_invalid_parameter_noinfo_noreturn`, которая вызывает функцию `_invalid_parameter` с пустыми параметрами, после чего вызывается функция `_invoke_watson` для принудительного завершения программы.

Функция `_invalid_parameter` проверяет наличие обработчика недопустимого параметра, определенного пользователем, и в случае обнаружения вызывает его. Например, если в текущем потоке пользователь определил локальный для потока обработчик, вызвав функцию [set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. Если пользователь определил глобальный обработчик недопустимого параметра, вызвав функцию [set_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md), вызывается этот обработчик, после чего функция возвращается. В противном случае вызывается обработчик по умолчанию `_invoke_watson`. По умолчанию `_invoke_watson` завершает работу программы. Определенные пользователем обработчики могут завершать работу программы или выполнять возврат. В тех случаях, когда восстановление работоспособности программы не гарантировано, рекомендуется завершать ее. 

Если при вызове обработчика по умолчанию `_invoke_watson` процессор поддерживает операцию [__fastfail](../../intrinsics/fastfail.md), вызов выполняется с параметром `FAST_FAIL_INVALID_ARG`, а процесс завершается. В противном случае возникает исключение с быстрым прекращением, которое может быть перехвачено с помощью связанного отладчика. Если продолжение процесса допускается, он завершается с помощью вызова функции Windows `TerminateProcess` с использованием состояния кода исключения `STATUS_INVALID_CRUNTIME_PARAMETER`. 

## <a name="requirements"></a>Требования  
|Функция|Обязательный заголовок|  
|--------------|------------------|  
|`_invalid_parameter`, `_invalid_parameter_noinfo`, `_invalid_parameter_noinfo_noreturn`, `_invoke_watson`|\<corecrt.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_get_invalid_parameter_handler, _get_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/get-invalid-parameter-handler-get-thread-local-invalid-parameter-handler.md)  
 [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](../../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)  
 [Проверка параметров](../../c-runtime-library/parameter-validation.md)
