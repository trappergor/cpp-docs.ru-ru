---
title: "_WriteBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_WriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WriteBarrier - встроенный объект"
  - "WriteBarrier - встроенный объект"
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _WriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Ограничивает оптимизации компилятора, которые могут изменить порядок операций доступа к памяти для точки вызова.  
  
> [!CAUTION]
>  Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует.  Для взаимодействия между потоками необходимо использовать такие механизмы, как [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) и [std::atomic\<T\>](../standard-library/atomic.md), определенные в [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md).  Для аппаратного доступа используйте параметр компилятора [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) с ключевым словом [volatile](../cpp/volatile-cpp.md).  
  
## Синтаксис  
  
```  
void _WriteBarrier(void);  
```  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_WriteBarrier`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Встроенная функция `_WriteBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_ReadWriteBarrier](../intrinsics/readwritebarrier.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)