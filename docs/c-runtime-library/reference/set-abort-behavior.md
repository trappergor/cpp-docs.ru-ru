---
title: _set_abort_behavior
ms.date: 01/02/2018
apiname:
- _set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: b72a485287684fc85f1e232e89774e07a5e3f42b
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927490"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

Указывает действие, выполняемое при аварийном завершении программы.

> [!NOTE]
> Не используйте функцию [Abort](abort.md) для завершения работы Microsoft Store приложения, за исключением сценариев тестирования или отладки. В соответствии с [политиками Microsoft Store](/legal/windows/agreements/store-policies)не разрешено закрывать приложения Магазина программным способом или с помощью пользовательского интерфейса. Дополнительные сведения см. в статье [жизненный цикл приложения UWP](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Новое значение флагов [прерывания](abort.md) .

*виде*<br/>
Маска для устанавливаемых битов флагов [прерывания](abort.md) .

## <a name="return-value"></a>Возвращаемое значение

Старое значение флагов.

## <a name="remarks"></a>Примечания

Существует два флага [прерывания](abort.md) : **_WRITE_ABORT_MSG** и **_CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** определяет, печатается ли полезное текстовое сообщение при аварийном завершении программы. В сообщении указывается, что приложение вызвало функцию [Abort](abort.md) . По умолчанию сообщение выводится. **_CALL_REPORTFAULT**(если задано) указывает, что создается дамп аварийной работы программы Watson и сообщается, когда вызывается метод [Abort](abort.md) . По умолчанию функция создания отчетов о аварийных дампах включена в неотладочных сборках.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>См. также

[abort](abort.md)<br/>
