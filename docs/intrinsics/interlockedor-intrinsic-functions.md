---
title: "Встроенные функции _InterlockedOr | Microsoft Docs"
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
  - "_InterlockedOr8_nf"
  - "_InterlockedOr_HLEAcquire"
  - "_InterlockedOr16_nf"
  - "_InterlockedOr64"
  - "_InterlockedOr8_np"
  - "_InterlockedOr64_cpp"
  - "_InterlockedOr8_acq"
  - "_InterlockedOr_nf"
  - "_InterlockedOr64_acq"
  - "_InterlockedOr_np"
  - "_InterlockedOr8"
  - "_InterlockedOr"
  - "_InterlockedOr64_np"
  - "_InterlockedOr_acq"
  - "_InterlockedOr64_HLERelease"
  - "_InterlockedOr16_np"
  - "_InterlockedOr_cpp"
  - "_InterlockedOr8_rel"
  - "_InterlockedOr64_rel"
  - "_InterlockedOr16_acq"
  - "_InterlockedOr_rel"
  - "_InterlockedOr16_rel"
  - "_InterlockedOr_HLERelease"
  - "_InterlockedOr64_HLEAcquire"
  - "_InterlockedOr16"
  - "_InterlockedOr64_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная  _InterlockedOr"
  - "Встроенная  _InterlockedOr_acq"
  - "Встроенная  _InterlockedOr_HLEAcquire"
  - "Встроенная  _InterlockedOr_HLERelease"
  - "Встроенная  _InterlockedOr_nf"
  - "Встроенная  _InterlockedOr_np"
  - "Встроенная  _InterlockedOr_rel"
  - "Встроенная  _InterlockedOr16"
  - "Встроенная  _InterlockedOr16_acq"
  - "Встроенная  _InterlockedOr16_nf"
  - "Встроенная  _InterlockedOr16_np"
  - "Встроенная  _InterlockedOr16_rel"
  - "Встроенная  _InterlockedOr64"
  - "Встроенная  _InterlockedOr64_acq"
  - "Встроенная  _InterlockedOr64_HLEAcquire"
  - "Встроенная  _InterlockedOr64_HLERelease"
  - "Встроенная  _InterlockedOr64_nf"
  - "Встроенная  _InterlockedOr64_np"
  - "Встроенная  _InterlockedOr64_rel"
  - "Встроенная  _InterlockedOr8"
  - "Встроенная  _InterlockedOr8_acq"
  - "Встроенная  _InterlockedOr8_nf"
  - "Встроенная  _InterlockedOr8_np"
  - "Встроенная  _InterlockedOr8_rel"
  - "Встроенная  InterlockedOr"
  - "Встроенная  InterlockedOr64"
ms.assetid: 5f265240-7af8-44b7-b952-19f3a9c56186
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Встроенные функции _InterlockedOr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Выполнение побитовой атомарной или операции над переменной, совместно используемой несколькими потоками.  
  
## Синтаксис  
  
```  
long _InterlockedOr(    long volatile * Value,    long Mask ); long _InterlockedOr_acq(    long volatile * Value,    long Mask ); long _InterlockedOr_HLEAcquire(    long volatile * Value,    long Mask ); long _InterlockedOr_HLERelease(    long volatile * Value,    long Mask ); long _InterlockedOr_nf(    long volatile * Value,    long Mask ); long _InterlockedOr_np(    long volatile * Value,    long Mask ); long _InterlockedOr_rel(    long volatile * Value,    long Mask ); char _InterlockedOr8(    char volatile * Value,    long Mask ); char _InterlockedOr8_acq(    char volatile * Value,    char Mask ); char _InterlockedOr8_nf(    char volatile * Value,    char Mask ); char _InterlockedOr8_np(    char volatile * Value,    char Mask ); char _InterlockedOr8_rel(    char volatile * Value,    char Mask ); short _InterlockedOr16(    short volatile * Value,    short Mask ); short _InterlockedOr16_acq(    short volatile * Value,    short Mask ); short _InterlockedOr16_nf(    short volatile * Value,    short Mask ); short _InterlockedOr16_np(    short volatile * Value,    short Mask ); short _InterlockedOr16_rel(    short volatile * Value,    short Mask ); __int64 _InterlockedOr64(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_acq(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedOr64_HLEAcquire(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_HLERelease(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedOr64_nf(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_np(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedOr64_rel(    __int64 volatile * Value,    __int64 Mask );  
```  
  
#### Параметры  
 \[in, out\] `Value`  
 Указатель на первый операнд заменяется результатом.  
  
 \[in\] `Mask`  
 Второй операнд.  
  
## Возвращаемое значение  
 Первый параметр указывает на исходное значение.  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_InterlockedOr` `_InterlockedOr8`, `_InterlockedOr16`, `_InterlockedOr64`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_InterlockedOr_acq`, `_InterlockedOr_nf`, `_InterlockedOr_rel`, `_InterlockedOr8_acq`, `_InterlockedOr8_nf`, `_InterlockedOr8_rel`, `_InterlockedOr16_acq`, `_InterlockedOr16_nf`, `_InterlockedOr16_rel`, `_InterlockedOr64_acq`, `_InterlockedOr64_nf`, `_InterlockedOr64_rel`|ARM|\< intrin.h \>|  
|`_InterlockedOr_np` `_InterlockedOr8_np`, `_InterlockedOr16_np`, `_InterlockedOr64_np`|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_InterlockedOr_HLEAcquire` `_InterlockedOr_HLERelease`, `_InterlockedOr64_HLEAcquire`, `_InterlockedOr64_HLERelease`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
  
## Заметки  
 Число в имени каждой функции указывает разрядность аргументов.  
  
 На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции.  Встроенные функции ARM с суффиксом `_nf` \(«без границ»\) не действуют как барьер памяти.  
  
 Встроенные функции с суффиксом `_np` \(«нет упреждающей выборки"\) запрещают возможную вставку компилятором операции упреждающей выборки.  
  
 На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision \(HLE\), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования.  Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.  
  
## Пример  
  
```  
// _InterlockedOr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedOr)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedOr(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xffffff00 0xffff00 0xff00ff00**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)