---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs:
- C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84e0f195bebd43ced767f05a7c6073a6d6e9db61
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408029"
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
 [_cwait](../c-runtime-library/reference/cwait.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)