---
title: "Встроенные функции _interlockedbittestandset | Microsoft Docs"
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
  - "_interlockedbittestandset_cpp"
  - "_interlockedbittestandset_HLEAcquire"
  - "_interlockedbittestandset64"
  - "_interlockedbittestandset"
  - "_interlockedbittestandset_rel"
  - "_interlockedbittestandset64_HLEAcquire"
  - "_interlockedbittestandset_HLERelease"
  - "_interlockedbittestandset_acq"
  - "_interlockedbittestandset_nf"
  - "_interlockedbittestandset64_cpp"
  - "_interlockedbittestandset64_HLERelease"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная _interlockedbittestandset"
  - "Встроенная _interlockedbittestandset64"
  - "Инструкция lock_bts"
ms.assetid: b1b7e334-53ea-48cf-ba60-5fa3ef51a1fc
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Встроенные функции _interlockedbittestandset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Создать инструкцию, которая проверяет разряд `b` адреса `a` и возвращает его текущее значение перед присваиванием 1.  
  
## Синтаксис  
  
```  
unsigned char _interlockedbittestandset(    long *a,    long b ); unsigned char _interlockedbittestandset_acq(    long *a,    long b ); unsigned char _interlockedbittestandset_HLEAcquire(    long *a,    long b ); unsigned char _interlockedbittestandset_HLERelease(    long *a,    long b ); unsigned char _interlockedbittestandset_nf(    long *a,    long b ); unsigned char _interlockedbittestandset_rel(    long *a,    long b ); unsigned char _interlockedbittestandset64(    __int64 *a,    __int64 b ); unsigned char _interlockedbittestandset64_HLEAcquire(    __int64 *a,    __int64 b ); unsigned char _interlockedbittestandset64_HLERelease(    __int64 *a,    __int64 b );  
```  
  
#### Параметры  
 \[in\] `a`  
 Указатель на область памяти для проверки.  
  
 \[in\] `b`  
 Позиция разряда для тестирования.  
  
## Возвращаемое значение  
 Значение разряда в позиции `b` перед присваиванием.  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_interlockedbittestandset`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM|\< intrin.h \>|  
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
|`_interlockedbittestandset64`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
  
## Заметки  
 На платформах процессоров x86 и [!INCLUDE[vcprx64](../Token/vcprx64_md.md)], эти встроенные функции используют инструкцию  `lock bts` для чтения и присваивания указанному разряду 1.  Эта операция является атомарной.  
  
 На процессорах ARM используются встроенные функции с суффиксами `_acq` и `_rel` для получения и освобождения семантики, например, в начале и конце критической секции.  Встроенные функции ARM с суффиксом `_nf` \(«без границ»\) не действуют как барьер памяти.  
  
 Для процессоров Intel, поддерживающих инструкции Hardware Lock Elision \(HLE\), встроенные функции с суффиксами`_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования.  Если эти встроенные функции вызываются на процессорах, не поддерживающих HLE, подсказка игнорируется.  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)