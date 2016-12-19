---
title: "Перечисление lock_when | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock_when"
  - "msclr.lock_when"
  - "lock_when"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock_when - перечисление"
ms.assetid: 6b87bbe9-63cd-450d-a02e-bb91ffd0dcea
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Перечисление lock_when
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает отложил блокирования.  
  
## Синтаксис  
  
```  
enum lock_when {  
   lock_later  
};  
```  
  
## Заметки  
 При передаче в [lock::lock](../dotnet/lock-lock.md), `lock_later` указывает, что блокировка не будет принятого ".  
  
## Пример  
 В этом примере используется единственный экземпляр класса через несколько потоков.  Класс использует блокировку для себя, чтобы обеспечить доступ к его внутренним данным согласуются для каждого потока.  Поток основного приложения использует блокировку на том же экземпляре класса периодически для проверки, чтобы определить наличие рабочие потоки все еще существуют, и ожидает, чтобы оставить, пока все рабочие потоки не будут завершения своих задач.  
  
```  
// msl_lock_lock_when.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
  **В потоке 3, счетчик \= 0**  
**В потоке 3, счетчик \= 10**  
**В потоке 5, счетчик \= 0**  
**В потоке 5, счетчик \= 10**  
**В потоке 7, счетчик \= 0**  
**В потоке 7, счетчик \= 10**  
**В потоке 4, счетчик \= 0**  
**В потоке 4, счетчик \= 10**  
**В потоке 6, счетчик \= 0**  
**В потоке 6, счетчик \= 10**  
**Все завершения потоков.**   
## Требования  
 **Файл заголовка**\<msclr\\lock.h\>  
  
 **Пространство имен** msclr  
  
## См. также  
 [lock](../dotnet/lock.md)