---
title: "Константы spawn | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_P_NOWAIT"
  - "_P_OVERLAY"
  - "_P_WAIT"
  - "_P_DETACH"
  - "_P_NOWAITO"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_P_DETACH - константа"
  - "_P_NOWAIT - константа"
  - "_P_NOWAITO - константа"
  - "_P_OVERLAY - константа"
  - "_P_WAIT - константа"
  - "P_DETACH - константа"
  - "P_NOWAIT - константа"
  - "P_NOWAITO - константа"
  - "P_OVERLAY - константа"
  - "P_WAIT - константа"
  - "spawn - константы"
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы spawn
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
#include <process.h>  
```  
  
## Заметки  
 Аргумент `mode` определяет действие, предпринимаемое процессом перед операцией инициализации и в течение нее.  Для `mode` возможны следующие значения:  
  
|Константа|Значение|  
|---------------|--------------|  
|`_P_OVERLAY`|Перекрывает вызывающий процесс новым процессом, уничтожающим вызывающий процесс \(тот же эффект, что и у вызова `_exec`\).|  
|`_P_WAIT`|Приостанавливает вызывающий поток до тех пор, пока выполнение нового процесса не будет закончено \(синхронный `_spawn`\).|  
|`_P_NOWAIT`, `_P_NOWAITO`|Продолжает выполнять вызывающий процесс одновременно с новым процессом \(асинхронный `_spawn`\).|  
|`_P_DETACH`|Продолжает выполнять вызывающий процесс; новый процесс выполняется в фоновом режиме без доступа к консоли или клавиатуре.  Вызывает `_cwait`, чтобы новый процесс не завершился неудачей.  Это асинхронный `_spawn`.|  
  
## См. также  
 [Функции \_spawn, \_wspawn](../Topic/_spawn,%20_wspawn%20Functions.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)