---
title: quick_exit1
ms.date: 11/04/2016
apiname:
- quick_exit
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
- quick_exit
- process/quick_exit
- stdlib/quick_exit
helpviewer_keywords:
- quick_exit function
ms.assetid: ecfbdae6-01c4-45fa-aaeb-b368e1de2a9c
ms.openlocfilehash: 50f1ee72cce04c2bebc8f7396a2b6fad98301dd7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429019"
---
# <a name="quickexit"></a>quick_exit

Приводит к завершению работы программы в обычном режиме.

## <a name="syntax"></a>Синтаксис

```C
__declspec(noreturn) void quick_exit(
    int status
);
```

### <a name="parameters"></a>Параметры

*status*<br/>
Код состояния, возвращаемый средой размещения.

## <a name="return-value"></a>Возвращаемое значение

**Quick_exit** функция не может возвращать его вызывающему.

## <a name="remarks"></a>Примечания

**Quick_exit** функции приводит к завершению программы в обычном режиме. Он не вызывает функции, зарегистрированные с **atexit**, **_onexit** или обработчики сигналов, зарегистрированные с **сигнала** функции. Если поведение не определено **quick_exit** вызывается несколько раз или если **выйти из** вызывается функция.

**Quick_exit** вызовы функций, в последний на входе, порядка поступления (LIFO), функции, зарегистрированные **at_quick_exit**, за исключением, что для этих функций, уже вызывается, когда функция была зарегистрирована.  Поведение не определено, если вызов [longjmp](longjmp.md) осуществляется во время вызова зарегистрированной функции, который привел бы к прерыванию вызова функции.

После вызова зарегистрированных функций **quick_exit** вызывает **_Exit** с помощью *состояние* значение, чтобы вернуть управление среде узла.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**quick_exit**|\<process.h> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[Функции _exec, _wexec](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[Функции _spawn, _wspawn](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
