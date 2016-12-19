---
title: "_InterlockedAddLargeStatistic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAddLargeStatistic"
  - "_InterlockedAddLargeStatistic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная функция _InterlockedAddLargeStatistic"
  - "Встроенная функция InterlockedAddLargeStatistic"
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedAddLargeStatistic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Выполняет сложение, предоставленное в котором первый операнд 64 \(sp2\) значение.  
  
## Синтаксис  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### Параметры  
 \[in, out\] `Addend`  
 Указатель на первый операнду в операцию добавления.  Значение заданное значение заменяется результатом сложения.  
  
 \[входящий\] `Value`  
 Второй операнд; значение, добавляемое к первому операнду.  
  
## Возвращаемое значение  
 Значение второго операнда.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Этот встроенный не атомн поскольку он реализован в виде отдельной инструкции блокированных 2.  Атомарное 64, происходит чтение в другом потоке при выполнении данного внутреннего элемента может привести к в несогласованном считываемого значения.  
  
 Эта функция работает аналогично барьера для чтения и записи.  Дополнительные сведения см. в разделе [\_ReadWriteBarrier](../intrinsics/readwritebarrier.md).  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)