---
title: "Встроенные функции _InterlockedCompareExchangePointer | Microsoft Docs"
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
  - "_InterlockedCompareExchangePointer_HLERelease"
  - "_InterlockedCompareExchangePointer_rel"
  - "_InterlockedCompareExchangePointer_acq_cpp"
  - "_InterlockedCompareExchangePointer"
  - "_InterlockedCompareExchangePointer_cpp"
  - "_InterlockedCompareExchangePointer_np"
  - "_InterlockedCompareExchangePointer_rel_cpp"
  - "_InterlockedCompareExchangePointer_HLEAcquire"
  - "_InterlockedCompareExchangePointer_acq"
  - "_InterlockedCompareExchangePointer_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная  _InterlockedCompareExchangePointer"
  - "Встроенная  _InterlockedCompareExchangePointer_acq"
  - "Встроенная  _InterlockedCompareExchangePointer_HLEAcquire"
  - "Встроенная  _InterlockedCompareExchangePointer_HLERelease"
  - "Встроенная  _InterlockedCompareExchangePointer_nf"
  - "Встроенная  _InterlockedCompareExchangePointer_np"
  - "Встроенная  _InterlockedCompareExchangePointer_rel"
  - "Встроенная  InterlockedCompareExchangePointer"
  - "Встроенная  InterlockedCompareExchangePointer_acq"
  - "Встроенная  InterlockedCompareExchangePointer_rel"
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Встроенные функции _InterlockedCompareExchangePointer
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Выполняет атомарную операцию, которая сохраняет адрес `Exchange` в адресе `Destination`, если адреса `Comparand` и `Destination` равны.  
  
## Синтаксис  
  
```  
void * _InterlockedCompareExchangePointer (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_acq (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLEAcquire (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLERelease (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_nf (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_np (    void * volatile * Destination,    void * Exchange,    void * Comparand ); long _InterlockedCompareExchangePointer_rel (    void * volatile * Destination,    void * Exchange,    void * Comparand );  
```  
  
#### Параметры  
 \[in, out\] `Destination`  
 Указатель на указатель на целевое значение.  Знак игнорируется  
  
 \[in\] `Exchange`  
 Указатель обмена.  Знак игнорируется  
  
 \[in\] `Comparand`  
 Указатель для сравнения с местом назначения.  Знак игнорируется  
  
## Возвращаемое значение  
 Возвращаемое значение является начальным значением места назначения.  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`_InterlockedCompareExchangePointer`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< intrin.h \>|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\< iiintrin.h \>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\< immintrin.h \>|  
  
## Заметки  
 `_InterlockedCompareExchangePointer` выполняет атомарное сравнение адреса `Destination` адрес с `Comparand` адресом.  Если адрес `Destination` равен адресу `Comparand`, адрес `Exchange` сохраняется в адресе, указанном в `Destination`.  В противном случае операция не выполняется.  
  
 `_InterlockedCompareExchangePointer` Обеспечивает поддержку встроенных функций компилятора для функции Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx).  
  
 Пример использования `_InterlockedCompareExchangePointer`, см. [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
 На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции.  Встроенные функции ARM с суффиксом `_nf` \(«без границ»\) не действуют как барьер памяти.  
  
 Встроенные функции с суффиксом `_np` \(«нет упреждающей выборки"\) запрещают возможную вставку компилятором операции упреждающей выборки.  
  
 На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision \(HLE\), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования.  Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)