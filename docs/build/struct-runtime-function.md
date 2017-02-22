---
title: "структура RUNTIME_FUNCTION | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# структура RUNTIME_FUNCTION
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для табличной обработки исключений требуется запись в таблице для каждой функции, выделяющей место в стеке или вызывающей другую функцию \(например, неконечные функции\).  Записи в таблице функций имеют следующий формат:  
  
|||  
|-|-|  
|ULONG|Начальный адрес функции|  
|ULONG|Конечный адрес функции|  
|ULONG|Адрес очистки|  
  
 Структура RUNTIME\_FUNCTION должна быть выровнена в памяти по типу DWORD.  Все адреса задаются относительно образа, то есть, они представляют собой 32\-разрядные смещения относительно стартового адреса образа, содержащего запись в таблице функций.  Эти записи сортируются и помещаются в раздел .pdata образа PE32\+.  Для динамически создаваемых функций \[JIT\-компиляторов\] среда выполнения для поддержки этих функций должна использовать RtlInstallFunctionTableCallback или RtlAddFunctionTable, чтобы предоставлять эти сведения операционной системе.  Невыполнение этого требования приведет к ненадежной обработке исключений и отладке процессов.  
  
## См. также  
 [Данные раскрутки для обработки исключений и поддержки отладчика](../build/unwind-data-for-exception-handling-debugger-support.md)