---
title: "Встроенные функции _InterlockedIncrement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedIncrement_acq"
  - "_InterlockedIncrement16_rel_cpp"
  - "_InterlockedIncrement16_cpp"
  - "_InterlockedIncrement64_rel"
  - "_InterlockedIncrement_rel"
  - "_InterlockedIncrement64_nf"
  - "_InterlockedIncrement16_acq_cpp"
  - "_InterlockedIncrement_rel_cpp"
  - "_InterlockedIncrement64"
  - "_InterlockedIncrement64_rel_cpp"
  - "_InterlockedIncrement16_nf"
  - "_InterlockedIncrement16_rel"
  - "_InterlockedIncrement16_acq"
  - "_InterlockedIncrement_nf"
  - "_InterlockedIncrement_acq_cpp"
  - "_InterlockedIncrement64_cpp"
  - "_InterlockedIncrement64_acq_cpp"
  - "_InterlockedIncrement"
  - "_InterlockedIncrement_cpp"
  - "_InterlockedIncrement64_acq"
  - "_InterlockedIncrement16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная  _InterlockedIncrement"
  - "Встроенная  _InterlockedIncrement_acq"
  - "Встроенная  _InterlockedIncrement_nf"
  - "Встроенная  _InterlockedIncrement_rel"
  - "Встроенная  _InterlockedIncrement16"
  - "Встроенная  _InterlockedIncrement16_acq"
  - "Встроенная  _InterlockedIncrement16_nf"
  - "Встроенная  _InterlockedIncrement16_rel"
  - "Встроенная  _InterlockedIncrement64"
  - "Встроенная  _InterlockedIncrement64_acq"
  - "Встроенная  _InterlockedIncrement64_nf"
  - "Встроенная  _InterlockedIncrement64_rel"
  - "Встроенная  InterlockedIncrement"
  - "Встроенная  InterlockedIncrement_acq"
  - "Встроенная  InterlockedIncrement_rel"
  - "Встроенная  InterlockedIncrement16"
  - "Встроенная  InterlockedIncrement64"
  - "Встроенная  InterlockedIncrement64_acq"
  - "Встроенная  InterlockedIncrement64_rel"
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Встроенные функции _InterlockedIncrement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Предоставляют встроенную поддержку компилятора для функции Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [InterlockedIncrement](http://msdn.microsoft.com/library/ms683614.aspx).  
  
## Синтаксис  
  
```  
long _InterlockedIncrement(  
   long * lpAddend  
);  
long _InterlockedIncrement_acq(  
   long * lpAddend  
);  
long _InterlockedIncrement_rel(  
   long * lpAddend  
);  
long _InterlockedIncrement_nf(  
   long * lpAddend  
);  
short _InterlockedIncrement16(  
   short * lpAddend  
);  
short _InterlockedIncrement16_acq(  
   short * lpAddend  
);  
short _InterlockedIncrement16_rel(  
   short * lpAddend  
);  
short _InterlockedIncrement16_nf (  
   short * lpAddend  
);  
__int64 _InterlockedIncrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedIncrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedIncrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### Параметры  
 \[in, out\] `lpAddend`  
 Указатель на переменную для увеличения.  
  
## Возвращаемое значение  
 Возвращаемое значение, полученное после увеличения.  
  
## Требования  
  
|Встроенная функция|Архитектура|Верхний колонтитул|  
|------------------------|-----------------|------------------------|  
|`_InterlockedIncrement`, `_InterlockedIncrement16`, `_InterlockedIncrement64`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM|\<intrin.h\>|  
  
## Заметки  
 Существуют несколько вариантов `_InterlockedIncrement`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.  
  
 Функция `_InterlockedIncrement` работает с 32\-разрядными целыми значениями, `_InterlockedIncrement16``_InterlockedIncrement64` работает с 16\-разрядными целыми значениями и работает с 64\-разрядными целыми значениями.  
  
 На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции.  Встроенная функция с суффиксом `_nf` \(«без границ»\) не действует как ограничитель памяти.  
  
 Переменная, на который указывает параметр `lpAddend`, должна быть выровнена по границе 32 разрядов; в противном случае эта функция не выполняется на многопроцессорных системах x86 и любой системе не\-x86.  Дополнительные сведения см. в [Выравнивание данных.](../cpp/align-cpp.md)  
  
 Функция Win32 объявляется в `Wdm.h` или `Ntddk.h`.  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## Пример  
 Пример использования `_InterlockedIncrement`, см. в [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)