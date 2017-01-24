---
title: "_callnewh | Microsoft Docs"
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
  - "_callnewh"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_callnewh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_callnewh"
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _callnewh
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает установленный в текущий момент *новый обработчик*.  
  
## Синтаксис  
  
```cpp  
int _callnewh(  
   size_t size  
   )  
  
```  
  
#### Параметры  
 `size`  
 Объем памяти, который [оператор new](../../cpp/new-operator-cpp.md) пытается выделить.  
  
## Возвращаемое значение  
  
|Значение|Описание|  
|--------------|--------------|  
|0|Сбой: Новый обработчик не установлен или нет активного нового обработчика.|  
|1|Успех: Новый обработчик установлен и активен.  Можно повторить попытку выделения памяти.|  
  
## Исключения  
 Эта функция генерирует [bad\_alloc](../../standard-library/bad-alloc-class.md), если *новый обработчик* не может быть размещен.  
  
## Заметки  
 *Новый обработчик* вызывается, если [оператор new](../../cpp/new-operator-cpp.md) не может выделить память.  Новый обработчик может затем инициировать некоторое подходящее действие, например, освобождение памяти, чтобы последующие попытки выделения памяти были успешны.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|\_callnewh|internal.h|  
  
## См. также  
 [\_set\_new\_handler](../Topic/_set_new_handler.md)   
 [\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md)