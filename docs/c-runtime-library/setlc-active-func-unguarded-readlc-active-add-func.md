---
title: "___setlc_active_func, ___unguarded_readlc_active_add_func | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "___unguarded_readlc_active_add_func"
  - "___setlc_active_func"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "___setlc_active_func"
  - "___unguarded_readlc_active_add_func"
ms.assetid: 605ec4e3-81e5-4ece-935a-f434768cc702
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ___setlc_active_func, ___unguarded_readlc_active_add_func
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

УСТАРЕВШИЕ.  Среда CRT экспортирует эти внутренние функции только для поддержания совместимости с двоичными данными.  
  
## Синтаксис  
  
```cpp  
int ___setlc_active_func(void); int * ___unguarded_readlc_active_add_func(void);  
```  
  
## Возвращаемое значение  
 Возвращаемое значение не важно.  
  
## Заметки  
 Хотя внутренние функции CRT `___setlc_active_func` и `___unguarded_readlc_active_add_func` являются устаревшими и более не используются, они экспортируются библиотекой CRT для поддержания совместимости с двоичными данными.  Изначальной целью функции `___setlc_active_func` был возврат числа текущих активных вызовов функции `setlocale`.  Изначальной целью функции `___unguarded_readlc_active_add_func` был возврат числа функций, которые ссылаются на языковой стандарт, не блокируя его.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`___setlc_active_func`, `___unguarded_readlc_active_add_func`|Нет|  
  
## См. также  
 [setlocale, \_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)