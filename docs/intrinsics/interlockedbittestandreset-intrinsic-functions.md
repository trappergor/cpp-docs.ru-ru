---
title: "встроенные функции _interlockedbittestandreset | Microsoft Docs"
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
  - "_interlockedbittestandreset_rel"
  - "_interlockedbittestandreset64"
  - "_interlockedbittestandreset64_HLERelease"
  - "_interlockedbittestandreset_HLERelease"
  - "_interlockedbittestandreset_HLEAcquire"
  - "_interlockedbittestandreset_acq"
  - "_interlockedbittestandreset_cpp"
  - "_interlockedbittestandreset_nf"
  - "_interlockedbittestandreset64_cpp"
  - "_interlockedbittestandreset64_HLEAcquire"
  - "_interlockedbittestandreset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная  _interlockedbittestandreset"
  - "Встроенная  _interlockedbittestandreset64"
  - "Инструкция lock_btr"
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# встроенные функции _interlockedbittestandreset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создает инструкцию, которая устанавливает разряд `b` адреса `a` в нулевое значение и возвращает исходное значение.  
  
## Синтаксис  
  
```  
unsigned char _interlockedbittestandreset(    long *a,    long b ); unsigned char _interlockedbittestandreset_acq(    long *a,    long b ); unsigned char _interlockedbittestandreset_HLEAcquire(    long *a,    long b ); unsigned char _interlockedbittestandreset_HLERelease(    long *a,    long b ); unsigned char _interlockedbittestandreset_nf(    long *a,    long b ); unsigned char _interlockedbittestandreset_rel(    long *a,    long b );  unsigned char _interlockedbittestandreset64(    __int64 *a,    __int64 b );  unsigned char _interlockedbittestandreset64_HLEAcquire(    __int64 *a,    __int64 b ); unsigned char _interlockedbittestandreset64_HLERelease(    __int64 *a,    __int64 b );  
```  
  
#### Параметры  
 \[in\] `a`  
 Указатель на область памяти для проверки.  
  
 \[in\] `b`  
 Позиция разряда для тестирования.  
  
## Возвращаемое значение  
 Исходное значение разряда в позиции, указанной параметром `b`.  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_interlockedbittestandreset`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\< intrin.h \>|  
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
|`_interlockedbittestandreset64`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
  
## Заметки  
 На платформах процессоров x86 и [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], их встроенные функции используют инструкцию `lock btr`, которая считывает и задает нулевое значение указанного разряда в атомарной операции.  
  
 На процессорах ARM используются встроенные функции с суффиксами `_acq` и `_rel` для получения и освобождения семантики, например, на начало и конец критической секции.  Встроенные функции ARM с суффиксом `_nf` \(«без границ»\) не действуют как барьер памяти.  
  
 Для процессоров Intel, поддерживающих инструкции Hardware Lock Elision \(HLE\), встроенные функции с суффиксами`_HLEAcquire` и `_HLERelease` включают подсказку к процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования.  Если эти встроенные функции вызываются на процессорах, не поддерживающих HLE, подсказка игнорируется.  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)