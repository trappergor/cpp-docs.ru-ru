---
title: Класс lock
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 43418da36aa2d87608a9d672e4345d24011be0b3
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805959"
---
# <a name="lock-class"></a>Класс lock

Этот класс позволяет автоматизировать блокировка для синхронизации доступа к объекту из нескольких потоков.  При создании получит блокировку и при уничтожении его выпуски блокировки.

## <a name="syntax"></a>Синтаксис

```cpp
ref class lock;
```

## <a name="remarks"></a>Примечания

`lock` доступен только для объектов среды CLR и может использоваться только в коде среды CLR.

На внутреннем уровне класс использует блокировки <xref:System.Threading.Monitor> для синхронизации доступа. Дополнительные сведения см. в разделе упоминаемой статьи.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|---------|-----------|
|[lock::lock](#lock)|Создает `lock` объекта, при необходимости ожидает получения блокировки неограниченно долго, в течение определенного времени или вообще не.|
|[lock::~lock](#tilde-lock)|Destructs `lock` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|---------|-----------|
|[lock::acquire](#acquire)|Получает блокировку для объекта, при необходимости ожидает получения блокировки неограниченно долго, в течение определенного времени или вообще не.|
|[lock::is_locked](#is-locked)|Указывает, находится ли блокировка.|
|[lock::release](#release)|Снимает блокировку.|
|[lock::try_acquire](#try-acquire)|Получает блокировку для объекта, в течение определенного времени ожидания и возврат `bool` чтобы сообщать об успехе приобретения, а не вызывает исключение.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание:|
|---------|-----------|
|[Lock::operator&nbsp;bool](#operator-bool)|Оператор для использования `lock` в условном выражении.|
|[lock::operator==](#operator-equality)|Оператор равенства.|
|[lock::operator!=](#operator-inequality)|Оператор неравенства.|

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\lock.h >

**Пространство имен** msclr



## <a name="lock"></a>Lock::LOCK

Создает `lock` объекта, при необходимости ожидает получения блокировки неограниченно долго, в течение определенного времени или вообще не.

```cpp
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

### <a name="parameters"></a>Параметры

*_Object*<br/>
Блокируемый объект.

*_timeout*<br/>
Значение времени ожидания в миллисекундах, или как <xref:System.TimeSpan>.

### <a name="exceptions"></a>Исключения

Создает <xref:System.ApplicationException> Если получение блокировки не происходит до истечения времени ожидания.

### <a name="remarks"></a>Примечания

Первые три формы конструктора попытке получения блокировки на `_object` в пределах заданного периода ожидания (или <xref:System.Threading.Timeout.Infinite> Если ничего не указано).

Четвертый конструктор в форме не получения блокировки на `_object`. `lock_later` является членом [lock_when-перечисление](../dotnet/lock-when-enum.md). Используйте [lock::acquire](../dotnet/lock-acquire.md) или [lock::try_acquire](../dotnet/lock-try-acquire.md) таким образом получить блокировку.

Блокировка будет выпущена автоматически в том случае, когда вызывается деструктор.

`_object` не может быть <xref:System.Threading.ReaderWriterLock>.  Если это так, приведет к ошибке компилятора.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками. Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса для периодической проверки для просмотра, если любой рабочих потоков по-прежнему существуют. Основное приложение затем ожидает, чтобы завершить работу до завершения своих задач все рабочие потоки.

```cpp
// msl_lock_lock.cpp
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

## <a name="tilde-lock"></a>Блокировка:: ~ блокировки

Destructs `lock` объекта.

```cpp
~lock();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает [lock::release](../dotnet/lock-release.md).

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками.  Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока.  Основной поток приложения использует блокировку на том же экземпляре класса для периодической проверки для просмотра, если любой рабочих потоков по-прежнему существуют. Основное приложение затем ожидает, чтобы завершить работу до завершения своих задач все рабочие потоки.

```cpp
// msl_lock_dtor.cpp
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

## <a name="acquire"></a>lock::acquire

Получает блокировку для объекта, при необходимости ожидает получения блокировки неограниченно долго, в течение определенного времени или вообще не.

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Параметры

*_timeout*<br/>
Значение времени ожидания в миллисекундах, или как <xref:System.TimeSpan>.

### <a name="exceptions"></a>Исключения

Создает <xref:System.ApplicationException> Если получение блокировки не происходит до истечения времени ожидания.

### <a name="remarks"></a>Примечания

Если значение времени ожидания не указан, по умолчанию — <xref:System.Threading.Timeout.Infinite>.

Если блокировка уже была получена, эта функция не выполняет никаких действий.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками.  Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса для периодической проверки для просмотра, если любой рабочих потоков по-прежнему существуют. Основное приложение затем ожидает, чтобы завершить работу до завершения своих задач все рабочие потоки.

```cpp
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

## <a name="is-locked"></a>lock::is_locked

Указывает, находится ли блокировка.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Возвращаемое значение

`true` Если блокировка, `false` в противном случае.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками.  Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока.  Основного потока приложения использует блокировку на том же экземпляре класса для периодической проверки любого рабочих потоков по-прежнему существовать, и ожиданий, чтобы завершить работу, пока все потоки исполнителей выполнили свои задачи.

```cpp
// msl_lock_is_locked.cpp
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
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l.is_locked()) { // check if we got the lock
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
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="operator-bool"></a>Lock::operator bool

Оператор для использования `lock` в условном выражении.

```cpp
operator bool();
```

### <a name="return-value"></a>Возвращаемое значение

`true` Если блокировка, `false` в противном случае.

### <a name="remarks"></a>Примечания

Этот оператор фактически преобразует `_detail_class::_safe_bool` которого является более безопасным, чем `bool` , так как он не может быть преобразован в целочисленный тип.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками.  Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса для периодической проверки для просмотра, если любой рабочих потоков по-прежнему существуют. Основное приложение ожидает, чтобы завершить работу до завершения своих задач все рабочие потоки.

```cpp
// msl_lock_op_bool.cpp
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
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l) { // use bool operator to check for lock
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

## <a name="release"></a>Lock::Release

Снимает блокировку.

```cpp
void release();
```

### <a name="remarks"></a>Примечания

Если блокировка не удерживается, `release` не выполняет никаких действий.

Не нужно явно вызывать эту функцию. Когда `lock` объект выходит за пределы области, его деструктор вызывает `release`.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками. Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса для периодической проверки для просмотра, если любой рабочих потоков по-прежнему существуют. Основное приложение затем ожидает, чтобы завершить работу до завершения своих задач все рабочие потоки.

```cpp
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

## <a name="try-acquire"></a>lock::try_acquire

Получает блокировку для объекта, в течение определенного времени ожидания и возврат `bool` чтобы сообщать об успехе приобретения, а не вызывает исключение.

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>Параметры

*_timeout*<br/>
Значение времени ожидания в миллисекундах, или как <xref:System.TimeSpan>.

### <a name="return-value"></a>Возвращаемое значение

`true` Если была получена блокировка, `false` в противном случае.

### <a name="remarks"></a>Примечания

Если блокировка уже была получена, эта функция не выполняет никаких действий.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса между несколькими потоками. Класс использует блокировку на себя, чтобы убедиться в том, что доступ к ее внутренним данным согласованы для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса для периодической проверки для просмотра, если любой рабочих потоков по-прежнему существуют. Основное приложение затем ожидает, чтобы завершить работу до завершения своих задач все рабочие потоки.

```cpp
// msl_lock_try_acquire.cpp
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

## <a name="operator-equality"></a>Lock::operator ==

Оператор равенства.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Объект для сравнения на равенство.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `true` Если `t` совпадает со значением объект блокировки, `false` в противном случае.

### <a name="example"></a>Пример

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="operator-inequality"></a>Lock::operator! =

Оператор неравенства.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Объект для сравнения на предмет их неравенства.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `true` Если `t` отличается от объект блокировки, `false` в противном случае.

### <a name="example"></a>Пример

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```