---
title: "Константы signal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SIGTERM"
  - "SIGFPE"
  - "SIGABRT"
  - "SIGILL"
  - "SIGINT"
  - "SIGSEGV"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SIGABRT - константа"
  - "SIGFPE - константа"
  - "SIGILL - константа"
  - "SIGINT - константа"
  - "константы сигналов"
  - "SIGSEGV - константа"
  - "SIGTERM - константа"
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Константы signal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
#include <signal.h>  
```  
  
## Заметки  
 Аргумент `sig` должен быть одной из перечисленных ниже констант \(определенных в SIGNAL.H\).  
  
 `SIGABRT`  
 Аварийное завершение.  Действие по умолчанию завершает вызывающую программу с кодом завершения 3.  
  
 `SIGABRT_COMPAT`  
 Аналогично SIGABRT.  Для совместимости с другими платформами.  
  
 `SIGFPE`  
 Ошибка в операции с плавающей запятой, например ошибка переполнения, деления на ноль или недопустимая операция.  Действие по умолчанию завершает вызывающую программу.  
  
 `SIGILL`  
 Недопустимая инструкция.  Действие по умолчанию завершает вызывающую программу.  
  
 `SIGINT`  
 Прерывание CTRL\+C.  Действие по умолчанию завершает вызывающую программу с кодом завершения 3.  
  
 `SIGSEGV`  
 Недопустимый доступ к хранилищу.  Действие по умолчанию завершает вызывающую программу.  
  
 `SIGTERM`  
 Программе отправлен запрос на завершение.  Действие по умолчанию завершает вызывающую программу с кодом завершения 3.  
  
 `SIG_ERR`  
 Возвращаемый тип сигнала, указывающего на случившуюся ошибку.  
  
## См. также  
 [signal](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)