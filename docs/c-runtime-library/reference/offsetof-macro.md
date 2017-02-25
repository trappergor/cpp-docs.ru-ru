---
title: "Макрос offsetof | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
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
  - "offsetof"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "offsetof - макрос"
  - "члены структуры, смещение"
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Макрос offsetof
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает смещение члена относительно начала его родительской структуры.  
  
## Синтаксис  
  
```  
  
        size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### Параметры  
 *structName*  
 Имя родительской структуры данных.  
  
 `memberName`  
 Имя члена в родительской структуре данных, для которого определяется смещение.  
  
## Возвращаемое значение  
 `offsetof` возвращает смещение в байтах указанного члена относительно начала его родительской структуры данных.  Для битовых полей оно будет неопределенным.  
  
## Заметки  
 Макрос `offsetof` возвращает смещение `memberName` в байтах относительно начала структуры, указанной в *structName*, как значение типа `size_t`.  С помощью ключевого слова `struct` можно указывать типы.  
  
> [!NOTE]
>  Макрос `offsetof` не является функцией и не может быть описан с помощью прототипа C.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`offsetof`|\<stddef.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)