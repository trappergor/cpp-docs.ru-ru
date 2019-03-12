---
title: Константы spawn
ms.date: 11/04/2016
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
ms.openlocfilehash: 988cc5e1b982f0c5577db77ae94f1df46c95ec0e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742756"
---
# <a name="spawn-constants"></a>Константы spawn

## <a name="syntax"></a>Синтаксис

```
#include <process.h>
```

## <a name="remarks"></a>Примечания

Аргумент `mode` определяет действие, предпринимаемое процессом перед операцией инициализации и в течение нее. Для `mode` возможны следующие значения:

|Константа|Значение|
|--------------|-------------|
|`_P_OVERLAY`|Перекрывает вызывающий процесс новым процессом, уничтожая вызывающий процесс (тот же эффект, что и у вызовов функции `_exec`).|
|`_P_WAIT`|Приостанавливает вызывающий поток до тех пор, пока не будет завершено выполнение нового процесса (синхронная функция `_spawn`).|
|`_P_NOWAIT`, `_P_NOWAITO`|Продолжает выполнять вызывающий процесс параллельно с новым процессом (асинхронная функция `_spawn`).|
|`_P_DETACH`|Продолжает выполнять вызывающий процесс; новый процесс выполняется в фоновом режиме без доступа к консоли или клавиатуре. Вызовы функции `_cwait` для нового процесса будут завершаться с ошибкой. Это асинхронная функция `_spawn`.|

## <a name="see-also"></a>См. также

[Функции _spawn, _wspawn](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
