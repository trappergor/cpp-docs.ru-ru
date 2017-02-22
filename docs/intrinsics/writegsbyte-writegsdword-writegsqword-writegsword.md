---
title: "__writegsbyte, __writegsdword, __writegsqword, __writegsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writegsbyte"
  - "__writegsqword"
  - "__writegsdword"
  - "__writegsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция __writegsqword"
  - "Встроенная функция __writegsbyte"
  - "Встроенная функция __writegsword"
  - "Встроенная функция __writegsdword"
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __writegsbyte, __writegsdword, __writegsqword, __writegsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Запишите память в место, указанное смещением относительно начала сегмента GS.  
  
## Синтаксис  
  
```  
void __writegsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writegsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writegsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writegsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### Параметры  
 \[входящий\] `Offset`  
 Смещение в байтах от начала GS для записи.  
  
 \[входящий\] `Data`  
 Записываемое значение.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__writegsbyte`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__writegsdword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__writegsqword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`__writegsword`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Эти встроенные функции доступны только в режиме ядра и эти подпрограммы доступны только в качестве встроенных функций.  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [\_\_readgsbyte, \_\_readgsdword, \_\_readgsqword, \_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)