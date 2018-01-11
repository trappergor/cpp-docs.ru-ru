---
title: "_set_abort_behavior | Документы Майкрософт"
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_abort_behavior
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
dev_langs: C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 965ff160fd8098c60f53f639cb95aedf890edd86
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="setabortbehavior"></a>_set_abort_behavior

Указывает действие, выполняемое при аварийном завершении программы.

> [!NOTE]
> Не используйте `abort` функции, чтобы завершить работу приложения магазина Microsoft, за исключением сценариев тестирования или отладки. Программный или пользовательского интерфейса способов закрыть приложение магазина, не разрешено согласно [банка политики](http://go.microsoft.com/fwlink/?LinkId=865936). Дополнительные сведения см. в разделе [жизненный цикл приложения UWP](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Параметры

[in] _флаги_  
Новое значение флагов `abort`.

[in] _маски_  
Маска для битов флагов `abort`, которую требуется задать.

## <a name="return-value"></a>Возвращаемое значение

Старое значение флагов.

## <a name="remarks"></a>Примечания

Существует два флага `abort`: `_WRITE_ABORT_MSG` и `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG` определяет, будет ли выводиться полезное текстовое сообщение при аварийном завершении программы. Сообщение указывает на то, что приложение вызвало функцию `abort`. По умолчанию сообщение выводится. Если задано, то `_CALL_REPORTFAULT` указывает, что создан аварийный дамп памяти Watson и отчет при вызове функции `abort`. По умолчанию функция создания отчетов о аварийных дампах включена в неотладочных сборках.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`_set_abort_behavior`|\<stdlib.h>|

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

[abort](../../c-runtime-library/reference/abort.md)  
