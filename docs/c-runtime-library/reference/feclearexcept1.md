---
title: "feclearexcept1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "feclearexcept"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "feclearexcept"
  - "fenv/feclearexcept"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функция feclearexcept"
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# feclearexcept
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предпринимается попытка очистить флаги исключения с плавающей запятой, указанный в аргументе.  
  
## Синтаксис  
  
```  
int feclearexcept(  
   int excepts  
);  
```  
  
#### Параметры  
 `excepts`  
 Флаги состояния исключения для очистки.  
  
## Возвращаемое значение  
 Возвращает нуль, если `excepts` равен нулю, или если все заданные исключения были успешно очищены. В противном случае — возвращает ненулевое значение.  
  
## Заметки  
 `feclearexcept` Функция попытки очистить с плавающей точки флаги состояния исключения, определяемое `excepts`. Функция поддерживает эти макросы исключений, определенных в fenv.h:  
  
|Исключение\-макрос|Описание|  
|------------------------|--------------|  
|FE\_DIVBYZERO|Произошла ошибка своеобразие или полюсе в ранее операции с плавающей запятой; значение бесконечности был создан.|  
|FE\_INEXACT|Функция была вынуждена округления хранимый результат ранее операции с плавающей запятой.|  
|FE\_INVALID|Ошибка домена в ранее операции с плавающей запятой.|  
|FE\_OVERFLOW|Ошибка диапазона; более ранние результат операции с плавающей запятой слишком велико для представления.|  
|FE\_UNDERFLOW|Ранее результат операции с плавающей запятой слишком мал для представления в точности; значение denormal был создан.|  
|FE\_ALLEXCEPT|Побитовое или всех поддерживаемых исключения с плавающей запятой.|  
  
 `excepts` Аргумент может иметь ноль или побитового или из одного или нескольких поддерживаемых исключение макросов. Результат любого другого значения аргумента не определено.  
  
## Требования  
  
|Функция|Заголовок C|Заголовок C\+\+|  
|-------------|-----------------|---------------------|  
|`feclearexcept`|\<fenv.h\>|\<cfenv\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## См. также  
 [Алфавитный указатель функций](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [fetestexcept](../Topic/fetestexcept1.md)