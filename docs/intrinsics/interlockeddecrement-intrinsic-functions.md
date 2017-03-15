---
title: "Встроенные функции _InterlockedDecrement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedDecrement16_rel_cpp"
  - "_InterlockedDecrement16_acq_cpp"
  - "_InterlockedDecrement16_rel"
  - "_InterlockedDecrement64_acq"
  - "_InterlockedDecrement_nf"
  - "_InterlockedDecrement16_nf"
  - "_InterlockedDecrement64_rel_cpp"
  - "_InterlockedDecrement_rel_cpp"
  - "_InterlockedDecrement16_acq"
  - "_InterlockedDecrement64_acq_cpp"
  - "_InterlockedDecrement_rel"
  - "_InterlockedDecrement64_nf"
  - "_InterlockedDecrement16_cpp"
  - "_InterlockedDecrement64"
  - "_InterlockedDecrement_cpp"
  - "_InterlockedDecrement64_rel"
  - "_InterlockedDecrement16"
  - "_InterlockedDecrement"
  - "_InterlockedDecrement64_cpp"
  - "_InterlockedDecrement_acq"
  - "_InterlockedDecrement_acq_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Встроенная  _InterlockedDecrement"
  - "Встроенная  _InterlockedDecrement_acq"
  - "Встроенная  _InterlockedDecrement_nf"
  - "Встроенная  _InterlockedDecrement_rel"
  - "Встроенная  _InterlockedDecrement16"
  - "Встроенная  _InterlockedDecrement16_acq"
  - "Встроенная  _InterlockedDecrement16_nf"
  - "Встроенная  _InterlockedDecrement16_rel"
  - "Встроенная  _InterlockedDecrement64"
  - "Встроенная  _InterlockedDecrement64_acq"
  - "Встроенная  _InterlockedDecrement64_nf"
  - "Встроенная  _InterlockedDecrement64_rel"
  - "Встроенная  InterlockedDecrement"
  - "Встроенная  InterlockedDecrement_acq"
  - "Встроенная  InterlockedDecrement_rel"
  - "Встроенная  InterlockedDecrement16"
  - "Встроенная  InterlockedDecrement64"
  - "Встроенная  InterlockedDecrement64_acq"
  - "Встроенная  InterlockedDecrement64_rel"
ms.assetid: 5268fce3-86b5-4b2b-b96c-2e531a3fb9b5
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Встроенные функции _InterlockedDecrement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Предоставляет встроенную поддержку компилятора для функции Win32 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] [InterlockedDecrement](http://msdn.microsoft.com/library/ms683580.aspx).  
  
## Синтаксис  
  
```  
long _InterlockedDecrement(  
   long * lpAddend  
);  
long _InterlockedDecrement_acq(  
   long * lpAddend  
);  
long _InterlockedDecrement_rel(  
   long * lpAddend  
);  
long _InterlockedDecrement_nf(  
   long * lpAddend  
);  
short _InterlockedDecrement16(  
   short * lpAddend  
);  
short _InterlockedDecrement16_acq(  
   short * lpAddend  
);  
short _InterlockedDecrement16_rel(  
   short * lpAddend  
);  
short _InterlockedDecrement16_nf(  
   short * lpAddend  
);  
__int64 _InterlockedDecrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedDecrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### Параметры  
 \[in, out\] `lpAddend`  
 Указатель на переменную для уменьшения.  
  
## Возвращаемое значение  
 Возвращаемое значение, полученное после уменьшения.  
  
## Требования  
  
|Встроенная функция|Архитектура|  
|------------------------|-----------------|  
|`_InterlockedDecrement`, `_InterlockedDecrement16`, `_InterlockedDecrement64`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM|  
  
 **Файл заголовка** \<intrin.h\>  
  
## Заметки  
 Существуют несколько вариантов `_InterlockedDecrement`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.  
  
 Функция `_InterlockedDecrement` работает с 32\-разрядными целыми значениями, `_InterlockedDecrement16``_InterlockedDecrement64` работает с 16\-разрядными целыми значениями и работает с 64\-разрядными целыми значениями.  
  
 На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции.  Встроенные функции с суффиксом `_nf` \(«без границ»\) не действуют как барьер памяти.  
  
 Переменная, на который указывает параметр `lpAddend`, должна быть выровнена по границе 32 разрядов; в противном случае эта функция не выполняется на многопроцессорных системах x86 и любой системе не\-x86.  Дополнительные сведения см. в [Выравнивание данных.](../cpp/align-cpp.md)  
  
 Эти процедуры доступны только как встроенные объекты.  
  
## Пример  
  
```  
// compiler_intrinsics_interlocked.cpp  
// compile with: /Oi  
#define _CRT_RAND_S  
  
#include <cstdlib>  
#include <cstdio>  
#include <process.h>  
#include <windows.h>  
  
// To declare an interlocked function for use as an intrinsic,  
// include intrin.h and put the function in a #pragma intrinsic   
// statement.  
#include <intrin.h>  
  
#pragma intrinsic (_InterlockedIncrement)  
  
// Data to protect with the interlocked functions.  
volatile LONG data = 1;  
  
void __cdecl SimpleThread(void* pParam);  
  
const int THREAD_COUNT = 6;  
  
int main() {  
   DWORD num;  
   HANDLE threads[THREAD_COUNT];  
   int args[THREAD_COUNT];  
   int i;  
  
   for (i = 0; i < THREAD_COUNT; i++) {  
     args[i] = i + 1;  
     threads[i] = reinterpret_cast<HANDLE>(_beginthread(SimpleThread, 0,   
                           args + i));  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
         // error creating threads  
         break;  
   }  
  
   WaitForMultipleObjects(i, threads, true, INFINITE);  
}  
  
// Code for our simple thread  
void __cdecl SimpleThread(void* pParam) {  
   int threadNum = *((int*)pParam);  
   int counter;  
   unsigned int randomValue;  
   unsigned int time;  
   errno_t err = rand_s(&randomValue);  
  
   if (err == 0) {  
      time = (unsigned int) ((double) randomValue / (double) UINT_MAX * 500);  
      while (data < 100) {  
         if (data < 100) {  
            _InterlockedIncrement(&data);  
            printf_s("Thread %d: %d\n", threadNum, data);  
         }  
  
         Sleep(time);   // wait up to half of a second  
      }  
   }  
  
   printf_s("Thread %d complete: %d\n", threadNum, data);  
}  
```  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Конфликты с компилятором x86](../Topic/Conflicts%20with%20the%20x86%20Compiler.md)