---
title: "_fmode | Microsoft Docs"
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
  - "fmode"
  - "_fmode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "перевод файла [C++], режим по умолчанию"
  - "Функция fmode"
  - "Функция _fmode"
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Переменная `_fmode` устанавливает режим преобразования файла по умолчанию в текстовый или бинарный.  Эта глобальная переменная не рекомендуются в силу наличия более безопасных функциональных версий [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) and [\_set\_fmode](../c-runtime-library/reference/set-fmode.md), которые должны использоваться вместо этой переменной.  Она объявляется в Stdlib.h следующим образом.  
  
## Синтаксис  
  
```  
extern int _fmode;  
```  
  
## Заметки  
 Параметр по умолчанию `_fmode` — `_O_TEXT` для преобразования в текстовом режиме.  `_O_BINARY` — параметр для бинарного режима.  
  
 Можно изменить значение `_fmode` тремя способами:  
  
-   Компоновка с Binmode.obj.  Это изменит начальный параметр `_fmode` в `_O_BINARY`, заставляя все файлы, кроме `stdin`, `stdout` и `stderr`, открываться в бинарном режиме.  
  
-   Вызвав `_get_fmode` или `_set_fmode` для получения или установки глобальной переменной `_fmode` соответственно.  
  
-   Изменить значение `_fmode` непосредственно в программе.  
  
## См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)