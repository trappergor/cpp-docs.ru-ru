---
title: _set_abort_behavior | Документы Майкрософт
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 299801cc4276118fc73a4be625a3df8cc84d58b2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43692938"
---
# <a name="setabortbehavior"></a>_set_abort_behavior

Указывает действие, выполняемое при аварийном завершении программы.

> [!NOTE]
> Не используйте [прервать](abort.md) функции, чтобы завершить работу в приложение Microsoft Store, за исключением сценариев тестирования или отладки. Закрытие приложения Store способов программным способом или пользовательского интерфейса не разрешены согласно [политики Microsoft Store](/legal/windows/agreements/store-policies). Дополнительные сведения см. в разделе [жизненный цикл приложения UWP](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Параметры

*flags*<br/>
Новое значение [прервать](abort.md) флаги.

*Маска*<br/>
Маска для [прервать](abort.md) флаги биты.

## <a name="return-value"></a>Возвращаемое значение

Старое значение флагов.

## <a name="remarks"></a>Примечания

Существует два [прервать](abort.md) флаги: **_WRITE_ABORT_MSG** и **_CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** определяет, печатается ли полезное текстовое сообщение при аварийном завершении программы. Сообщение о том, что приложение вызвало [прервать](abort.md) функции. По умолчанию сообщение выводится. **_CALL_REPORTFAULT**, если значение, указывает, что аварийный дамп памяти Watson и отчет при [прервать](abort.md) вызывается. По умолчанию функция создания отчетов о аварийных дампах включена в неотладочных сборках.

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
