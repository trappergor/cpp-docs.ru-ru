---
title: "Встроенные функции _InterlockedExchangeAdd | Microsoft Docs"
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
  - "_InterlockedExchangeAdd64_nf"
  - "_InterlockedExchangeAdd64_rel"
  - "_InterlockedExchangeAdd16_rel"
  - "_InterlockedExchangeAdd_acq"
  - "_InterlockedExchangeAdd_nf"
  - "_InterlockedExchangeAdd_rel"
  - "_InterlockedExchangeAdd8_acq"
  - "_InterlockedExchangeAdd16_nf"
  - "_InterlockedExchangeAdd_acq_cpp"
  - "_InterlockedExchangeAdd64_acq_cpp"
  - "_InterlockedExchangeAdd16_acq"
  - "_InterlockedExchangeAdd_HLERelease"
  - "_InterlockedExchangeAdd64_cpp"
  - "_InterlockedExchangeAdd64_HLERelease"
  - "_InterlockedExchangeAdd64_acq"
  - "_InterlockedExchangeAdd8"
  - "_InterlockedExchangeAdd64"
  - "_InterlockedExchangeAdd8_nf"
  - "_InterlockedExchangeAdd16"
  - "_InterlockedExchangeAdd64_rel_cpp"
  - "_InterlockedExchangeAdd_cpp"
  - "_InterlockedExchangeAdd8_rel"
  - "_InterlockedExchangeAdd_HLEAcquire"
  - "_InterlockedExchangeAdd64_HLEAcquire"
  - "_InterlockedExchangeAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная  _InterlockedExchangeAdd"
  - "Встроенная  _InterlockedExchangeAdd_acq"
  - "Встроенная  _InterlockedExchangeAdd_HLEAcquire"
  - "Встроенная  _InterlockedExchangeAdd_HLERelease"
  - "Встроенная  _InterlockedExchangeAdd_nf"
  - "Встроенная  _InterlockedExchangeAdd_rel"
  - "Встроенная  _InterlockedExchangeAdd16"
  - "Встроенная  _InterlockedExchangeAdd16_acq"
  - "Встроенная  _InterlockedExchangeAdd16_nf"
  - "Встроенная  _InterlockedExchangeAdd16_rel"
  - "Встроенная  _InterlockedExchangeAdd64"
  - "Встроенная  _InterlockedExchangeAdd64_acq"
  - "Встроенная  _InterlockedExchangeAdd64_HLEAcquire"
  - "Встроенная  _InterlockedExchangeAdd64_HLERelease"
  - "Встроенная  _InterlockedExchangeAdd64_nf"
  - "Встроенная  _InterlockedExchangeAdd64_rel"
  - "Встроенная  _InterlockedExchangeAdd8"
  - "Встроенная  _InterlockedExchangeAdd8_acq"
  - "Встроенная  _InterlockedExchangeAdd8_nf"
  - "Встроенная  _InterlockedExchangeAdd8_rel"
  - "Встроенная  InterlockedExchangeAdd"
  - "Встроенная  InterlockedExchangeAdd_acq"
  - "Встроенная  InterlockedExchangeAdd_rel"
  - "Встроенная  InterlockedExchangeAdd64"
  - "Встроенная  InterlockedExchangeAdd64_acq"
  - "Встроенная  InterlockedExchangeAdd64_rel"
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Встроенные функции _InterlockedExchangeAdd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Обеспечивает встроенную поддержку компилятором функции Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedExchangeAdd Intrinsic Functions](../intrinsics/interlockedexchangeadd-intrinsic-functions.md).  
  
## Синтаксис  
  
```  
long _InterlockedExchangeAdd(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_acq(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_rel(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_nf(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLEAcquire(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLERelease(    long volatile * Addend,    long Value ); char _InterlockedExchangeAdd8(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_acq(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_rel(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_nf(    char volatile * Addend,    char Value ); short _InterlockedExchangeAdd16(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_acq(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_rel(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_nf(    short volatile * Addend,    short Value ); __int64 _InterlockedExchangeAdd64(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_acq(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_rel(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_nf(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLEAcquire(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLERelease(    __int64 volatile * Addend,    __int64 Value );   
```  
  
#### Параметры  
 \[in, out\] `Addend`  
 Значение для сложения; заменяется результатом сложения.  
  
 \[in\] `Value`  
 Значение для сложения.  
  
## Возвращаемое значение  
 Возвращает начальное значение переменной, на которую указывает параметр`Addend` .  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_InterlockedExchangeAdd` `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`, `_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\< intrin.h \>|  
|`_InterlockedExchangeAdd_HLEAcquire` `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
  
## Заметки  
 Существуют несколько вариантов `_InterlockedExchangeAdd`, они различаются в зависимости от типов данных, которые включают,  и от того, используется ли семантика получения или освобождения конкретного процессора.  
  
 Функция `_InterlockedExchangeAdd` работает с 32\-разрядными целыми значениями, `_InterlockedExchangeAdd8`работает с 8\-разрядными целыми значениями, `_InterlockedExchangeAdd16` работает с 16\-разрядными целыми значениями и `_InterlockedExchangeAdd64` работает с 64\-разрядными целыми значениями.  
  
 На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции.  Встроенные функции с суффиксом `_nf` \(«без границ»\) не действуют как барьер памяти.  
  
 На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision \(HLE\), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования.  Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.  
  
 Эти процедуры доступны только как встроенные объекты.  Таким образом, они являются встроенными, вне зависимости от того, используется ли [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md) или [\#pragma intrinsic](../preprocessor/intrinsic.md) .  Невозможно использовать [\#pragma function](../preprocessor/function-c-cpp.md) на этих встроенных функций.  
  
## Пример  
 Пример использования `_InterlockedExchangeAdd`, см. [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)