---
title: "__readgsbyte, __readgsdword, __readgsqword, __readgsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readgsbyte"
  - "__readgsdword"
  - "__readgsqword"
  - "__readgsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __readgsword"
  - "Встроенная функция __readgsdword"
  - "Встроенная функция __readgsqword"
  - "Встроенная функция __readgsbyte"
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __readgsbyte, __readgsdword, __readgsqword, __readgsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Память для чтения начиная с позиции, указанной смещением относительно начала сегмента GS.  
  
## Синтаксис  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### Параметры  
 \[входящий\] `Offset`  
 Смещение в байтах от начала `GS`, из которого выполняется чтение.  
  
## Возвращаемое значение  
 Содержимое памяти в байтах, слова, повторяющегося слова или quadword \(как показано в разделе имя вызываемой функции\) на месте `GS:[``Offset``]`.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__readgsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__readgsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__readgsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__readgsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Эти встроенные функции доступны только в режиме ядра и подпрограммы доступны только в качестве встроенных функций.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [\_\_writegsbyte, \_\_writegsdword, \_\_writegsqword, \_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)