---
title: "_acmdln, _tcmdln, _wcmdln | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wcmdln"
  - "_acmdln"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_acmdln"
  - "acmdln"
  - "_wcmdln"
  - "wcmdln"
  - "_tcmdln"
  - "tcmdln"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_acmdln - глобальная переменная"
  - "_tcmdln - глобальная переменная"
  - "_wcmdln - глобальная переменная"
  - "acmdln - глобальная переменная"
  - "tcmdln - глобальная переменная"
  - "wcmdln - глобальная переменная"
ms.assetid: 4fc0a6a0-3f93-420a-a19f-5276061ba539
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# _acmdln, _tcmdln, _wcmdln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внутренняя глобальная переменная CRT.  Командная строка.  
  
## Синтаксис  
  
```  
char * _acmdln; wchar_t * _wcmdln;  #ifdef WPRFLAG    #define _tcmdln _wcmdln #else    #define _tcmdln _acmdln  
```  
  
## Заметки  
 Эти внутренние переменные CRT хранят полную командную строку.  Они предоставляются в экспортируемых символах для CRT, но не предназначены для использования в коде.  `_acmdln` хранит данные как строку символов.  `_wcmdln` хранит данные как строку расширенных символов.  `_tcmdln` может быть определена как `_acmdln` или `_wcmdln` в зависимости от обстоятельств.  
  
## См. также  
 [Глобальные переменные](../c-runtime-library/global-variables.md)