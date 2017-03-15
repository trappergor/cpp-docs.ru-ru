---
title: "__incgsbyte, __incgsword, __incgsdword, __incgsqword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__incgsdword"
  - "__incgsqword_cpp"
  - "__incgsword_cpp"
  - "__incgsword"
  - "__incgsbyte"
  - "__incgsbyte_cpp"
  - "__incgsqword"
  - "__incgsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __incgsbyte"
  - "Встроенная функция __incgsword"
  - "Встроенная функция __incgsqword"
  - "Встроенная функция __incgsdword"
ms.assetid: 06bfdf4f-7643-4fe0-8455-60ce3068073e
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __incgsbyte, __incgsword, __incgsdword, __incgsqword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Добавьте одно значение на области памяти заданным смещением относительно начала сегмента `GS`.  
  
## Синтаксис  
  
```  
void __incgsbyte(   
   unsigned long Offset   
);  
void __incgsword(   
   unsigned long Offset   
);  
void __incgsdword(   
   unsigned long Offset  
);  
void __incgsqword(   
   unsigned long Offset   
);  
```  
  
#### Параметры  
 \[входящий\] `Offset`  
 Смещение в байтах от начала `GS`.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__incgsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__incgsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__incgsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__incgsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
## Заметки  
 Эти встроенные функции доступны только в режиме ядра и подпрограммы доступны только в качестве встроенных функций.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [\_\_addgsbyte, \_\_addgsword, \_\_addgsdword, \_\_addgsqword](../intrinsics/addgsbyte-addgsword-addgsdword-addgsqword.md)   
 [\_\_readgsbyte, \_\_readgsdword, \_\_readgsqword, \_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [\_\_writegsbyte, \_\_writegsdword, \_\_writegsqword, \_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)