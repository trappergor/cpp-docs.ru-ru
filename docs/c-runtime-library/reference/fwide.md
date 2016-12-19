---
title: "fwide | Microsoft Docs"
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
  - "fwide"
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
apitype: "DLLExport"
f1_keywords: 
  - "fwide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fwide - функция"
ms.assetid: a4641f5b-d74f-4946-95d5-53a64610d28d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fwide
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Не реализовано.  
  
## Синтаксис  
  
```  
int fwide(  
   FILE *stream,  
   int mode;  
);  
```  
  
#### Параметры  
 `stream`  
 Указатель на структуру `FILE` \(игнорируется\).  
  
 `mode`  
 Новая ширина потока: положительная для расширенных символов, отрицательная для byte, ноль, если оставить неизменной. \(Это значение игнорируется.\)  
  
## Возвращаемое значение  
 Эта функция в данный момент просто возвращает `mode`.  
  
## Заметки  
 Текущая версия этой функции не соответствуют стандарту.  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`fwide`|\<wchar.h\>|  
  
 Для получения дополнительной информации см. [Совместимость](../../c-runtime-library/compatibility.md).