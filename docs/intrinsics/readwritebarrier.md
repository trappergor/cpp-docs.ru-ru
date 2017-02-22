---
title: "_ReadWriteBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadWriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadWriteBarrier - встроенный объект"
  - "ReadWriteBarrier - встроенный объект"
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _ReadWriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Ограничивает оптимизации компилятора, которые могут изменить порядок доступа к памяти для точки вызова.  
  
> [!CAUTION]
>  Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует.  Для взаимодействия между потоками необходимо использовать такие механизмы, как [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) и [std::atomic\<T\>](../standard-library/atomic.md), определенные в [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md).  Для аппаратного доступа используйте параметр компилятора [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) с ключевым словом [volatile](../cpp/volatile-cpp.md).  
  
## Синтаксис  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_ReadWriteBarrier`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Встроенная функция `_ReadWriteBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_WriteBarrier](../intrinsics/writebarrier.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)