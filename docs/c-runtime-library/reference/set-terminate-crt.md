---
title: set_terminate (CRT)
ms.date: 4/2/2020
api_name:
- set_terminate
- _o_set_terminate
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 08ea5bb8c446fadac6a7bcf7ca172c5d14546776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332106"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

Устанавливает свой собственный режим прекращения, который будет вызван **окончанием.**

## <a name="syntax"></a>Синтаксис

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Параметры

*termFunction*<br/>
Указатель на пользовательскую функцию завершения.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию, зарегистрированную **set_terminate,** чтобы предыдущая функция была восстановлена позже. Если предыдущая функция не установлена, значение возврата может быть использовано для восстановления поведения по умолчанию; это значение может быть **NULL**.

## <a name="remarks"></a>Remarks

Функция **set_terminate** устанавливает *termFunction* как функцию, вызванную **завершением.** **set_terminate** используется при обработке исключений с саии и может быть вызван в любой момент вашей программы до того, как будет сделано исключение. **прекратить** [выполнение](abort.md) вызовов по умолчанию. Вы можете изменить этот дефолт, написав собственную функцию прекращения и вызывая **set_terminate** с именем вашей функции в качестве аргумента. **прекратить** вызовы последней функции, данной в качестве аргумента для **set_terminate.** После выполнения любых желаемых задач очистки, *termFunction* должен выйти из программы. Если он не выходит (если он возвращается к вызывающему), [прерывается](abort.md) прерывание.

В многопоточной среде функции завершения поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции завершения. Таким образом, каждый поток отвечает за собственную обработку завершения.

Тип **terminate_function** определяется в EH. H как указатель на функцию прерывания, определяемую пользователем, *termFunction,* которая возвращает **пустоту.** Ваш пользовательский *термин функцииFunction* не может принимать никаких аргументов и не должен возвращаться к своему абоненту. Если это так, [прерывание](abort.md) называется. Исключение не может быть брошено из *termFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Функция set_terminate** работает только за пределами отладчика.

Существует единый **обработчик set_terminate** для всех динамически связанных DLLs или EXEs; даже если вы **позвоните set_terminate** ваш обработчик может быть заменен другим, или вы можете заменить обработчик, установленный другим DLL или EXE.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для функции [terminate](terminate-crt.md).

## <a name="see-also"></a>См. также раздел

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[Прервать](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Прекратить](terminate-crt.md)<br/>
[Неожиданные](unexpected-crt.md)<br/>
