---
title: _set_abort_behavior
ms.date: 4/2/2020
api_name:
- _set_abort_behavior
- _o__set_abort_behavior
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
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: fd3a3c2f99d1702cdccf68328c2122b965b2d078
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337872"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

Указывает действие, выполняемое при аварийном завершении программы.

> [!NOTE]
> Не используйте функцию [прерывания](abort.md) для закрытия приложения Microsoft Store, за исключением сценариев тестирования или отладки. Программные или утилиты для использования не допускаются в соответствии с [правилами Microsoft Store.](/legal/windows/agreements/store-policies) Для получения дополнительной [UWP app lifecycle](/windows/uwp/launch-resume/app-lifecycle)информации см.

## <a name="syntax"></a>Синтаксис

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Параметры

*Флаги*<br/>
Новое значение [флагов прерывания.](abort.md)

*маска*<br/>
Маска для [прерывания](abort.md) флаги биты установить.

## <a name="return-value"></a>Возвращаемое значение

Старое значение флагов.

## <a name="remarks"></a>Remarks

Есть два [флага прерывания:](abort.md) **_WRITE_ABORT_MSG** и **_CALL_REPORTFAULT.** **_WRITE_ABORT_MSG** определяет, печатается ли полезное текстовое сообщение, когда программа ненормально прекращена. В сообщении говорится, что приложение вызвало функцию [прерывания.](abort.md) По умолчанию сообщение выводится. **_CALL_REPORTFAULT,** если набор, указывает, что сброс аварии Watson генерируется и сообщается, когда [прерывание](abort.md) вызывается. По умолчанию функция создания отчетов о аварийных дампах включена в неотладочных сборках.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Прервать](abort.md)<br/>
