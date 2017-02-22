---
title: "__max | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__max"
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
  - "max"
  - "__max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__max - макрос"
  - "max - макрос"
  - "maximum - макрос"
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __max
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает наибольшее из двух значений .  
  
## Синтаксис  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### Параметры  
 `type`  
 Любой числовой тип данных  
  
 `a, b`  
 Значения любого числового типа для сравнения.  
  
## Возвращаемое значение  
 `__max` возвращает наибольшее из его аргументов.  
  
## Заметки  
 Макрос `__max` сравнивает два значения и возвращает значение большего.  Аргументы могут быть любого числового типа данных со знаком или без знака.  И аргументы и возвращаемое значение должны иметь одинаковый тип данных.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`__max`|\<stdlib.h\>|  
  
## Пример  
 Дополнительные сведения см. в примере [\_\_min](../../c-runtime-library/reference/min.md).  
  
## Эквивалент в .NET Framework  
 [System::Math::Max](https://msdn.microsoft.com/en-us/library/system.math.max.aspx)  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [\_\_min](../../c-runtime-library/reference/min.md)