---
title: _WAIT_CHILD, _WAIT_GRANDCHILD
ms.date: 11/04/2016
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
ms.openlocfilehash: 714b4e79f1c229817a12908aad0d726f74023036
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524395"
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD

## <a name="syntax"></a>Синтаксис

```

#include <process.h>
```

## <a name="remarks"></a>Примечания

Функция `_cwait` может использоваться любым процессом для ожидания любого другого процесса (если известен его идентификатор). Аргумент действия может принимать одно из следующих значений:

|Константа|Значение|
|--------------|-------------|
|`_WAIT_CHILD`|Вызывающий процесс ожидает завершения указанного нового процесса.|
|`_WAIT_GRANDCHILD`|Вызывающий процесс ожидает завершения указанного нового процесса и всех процессов, созданных этим новым процессом.|

## <a name="see-also"></a>См. также

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)