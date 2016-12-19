---
title: "__CxxFrameHandler | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__CxxFrameHandler"
apilocation: 
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__CxxFrameHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__CxxFrameHandler"
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __CxxFrameHandler
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренняя функция CRT.  Используется CRT для обработки кадров структурированной обработки исключений.  
  
## Синтаксис  
  
```cpp  
EXCEPTION_DISPOSITION __CxxFrameHandler(       EHExceptionRecord  *pExcept,       EHRegistrationNode *pRN,       void               *pContext,        DispatcherContext  *pDC    )  
```  
  
#### Параметры  
 `pExcept`  
 Запись исключения, передаваемая в возможные операторы `catch`.  
  
 `pRN`  
 Динамические сведения о кадре стека, который используется для обработки исключения.  Дополнительные сведения см. в описании ehdata.h.  
  
 `pContext`  
 Контекст.  \(Не используется для процессоров Intel.\)  
  
 `pDC`  
 Дополнительные сведения о входе в функцию и кадре стека.  
  
## Возвращаемое значение  
 Одно из значений *выражения фильтра*, используемое [Оператор try\-except](../cpp/try-except-statement.md).  
  
## Заметки  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|\_\_CxxFrameHandler|excpt.h, ehdata.h|