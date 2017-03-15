---
title: "_WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_WAIT_GRANDCHILD"
  - "WAIT_CHILD"
  - "WAIT_GRANDCHILD"
  - "_WAIT_CHILD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WAIT_CHILD - константа"
  - "_WAIT_GRANDCHILD - константа"
  - "WAIT_CHILD - константа"
  - "WAIT_GRANDCHILD - константа"
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# _WAIT_CHILD, _WAIT_GRANDCHILD
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <process.h>  
  
```  
  
## Заметки  
 Функция `_cwait` может использоваться любым процессом для ожидания любого другого процесса \(если известен идентификатор процесса\).  Этот аргумент действия может быть равен одному из следующих значений:  
  
|Константа|Значение|  
|---------------|--------------|  
|`_WAIT_CHILD`|Вызывающий процесс ожидает, пока указанный новый процесс не завершится.|  
|`_WAIT_GRANDCHILD`|Вызывающий процесс ожидает, пока указанный новый процесс и все процессы, созданный этим новым процессом, не завершатся.|  
  
## См. также  
 [\_cwait](../c-runtime-library/reference/cwait.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)