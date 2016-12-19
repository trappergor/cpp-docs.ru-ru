---
title: "Константы действий signal | Microsoft Docs"
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
  - "SIG_IGN"
  - "SIG_DFL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "SIG_DFL - константа"
  - "SIG_IGN - константа"
  - "константы действий сигналов"
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы действий signal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выполняемое после получения сигнала прерывания действие зависит от значения `func`.  
  
## Синтаксис  
  
```  
#include <signal.h>  
```  
  
## Заметки  
 Аргумент `func` должен быть либо адресом функции или одной из констант манифеста, перечисленных ниже и определенных в SIGNAL.H.  
  
 `SIG_DFL`  
 Использует системный отклик по умолчанию.  Если вызывающая программа использует поток ввода\-вывода, буферы, созданные библиотекой среды выполнения не сбрасываются.  
  
 `SIG_IGN`  
 Игнорирует сигнал прерывания.  Это значение никогда не следует предоставлять для `SIGFPE`, поскольку состояние процесса с плавающей запятой остается не определенным.  
  
 `SIG_SGE`  
 Указывает, что произошла ошибка в сигнале.  
  
 `SIG_ACK`  
 Указывает, что было получено подтверждение.  
  
 `SIG_ERR`  
 Возвращаемый тип сигнала, указывающего на случившуюся ошибку.  
  
## См. также  
 [signal](../c-runtime-library/reference/signal.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)