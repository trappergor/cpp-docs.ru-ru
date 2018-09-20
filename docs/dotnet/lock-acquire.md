---
title: Lock::acquire | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock::acquire
- acquire
- msclr.lock.acquire
- msclr::lock::acquire
- lock.acquire
dev_langs:
- C++
helpviewer_keywords:
- acquire method
ms.assetid: c214274e-7519-4739-82aa-91b04a32d3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0a1bc71e4474f0d7d22d217adb96aa7340fb933b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409172"
---
# <a name="lockacquire"></a>lock::acquire

Получает блокировку для объекта, при необходимости ожидает получения блокировки неограниченно долго, в течение определенного времени или вообще не.

## <a name="syntax"></a>Синтаксис

```
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

#### <a name="parameters"></a>Параметры

*_время ожидания*<br/>
Значение времени ожидания в миллисекундах, или как <xref:System.TimeSpan>.

## <a name="exceptions"></a>Исключения

Создает <xref:System.ApplicationException> Если получение блокировки не происходит до истечения времени ожидания.

## <a name="remarks"></a>Примечания

Если значение времени ожидания не задан, по умолчанию — <xref:System.Threading.Timeout.Infinite>.

Если блокировка уже была получена, эта функция не выполняет никаких действий.

## <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Этот класс использует блокировку на себя для обеспечения согласованности для каждого потока, доступ к ее внутренним данным.  Основного потока приложения использует блокировку на том же экземпляре класса для периодической проверки любого рабочих потоков по-прежнему существовать, и ожиданий, чтобы завершить работу, пока все потоки исполнителей выполнили свои задачи.

```
// msl_lock_acquire.cpp
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
[lock::try_acquire](../dotnet/lock-try-acquire.md)