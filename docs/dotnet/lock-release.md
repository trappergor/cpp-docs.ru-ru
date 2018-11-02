---
title: lock::release
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock.release
- msclr::lock::release
- lock::release
- msclr.lock.release
helpviewer_keywords:
- lock::release
ms.assetid: b73d48fc-cf98-4b78-b39d-813d4a12fa84
ms.openlocfilehash: 2fdb3ab6f261aa4752911a93d5f5ae0f5d637f44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650375"
---
# <a name="lockrelease"></a>lock::release

Снимает блокировку.

## <a name="syntax"></a>Синтаксис

```
void release();
```

## <a name="remarks"></a>Примечания

Если блокировка не удерживается, `release` не выполняет никаких действий.

У вас нет вызов этой функции явным образом; Когда `lock` объект выходит за пределы области, его деструктор вызывает `release`.

## <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Этот класс использует блокировку на себя для обеспечения согласованности для каждого потока, доступ к ее внутренним данным.  Основного потока приложения использует блокировку на том же экземпляре класса для периодической проверки любого рабочих потоков по-прежнему существовать, и ожиданий, чтобы завершить работу, пока все потоки исполнителей выполнили свои задачи.

```
// msl_lock_release.cpp
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

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\lock.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[Члены lock](../dotnet/lock-members.md)<br/>
[lock::~lock](../dotnet/lock-tilde-lock.md)