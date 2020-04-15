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
ms.openlocfilehash: ea09dd3d4a2eaf4cf7708d09509cfecfa4a6c6d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373067"
---
# <a name="lock-class"></a>Класс lock

Этот класс автоматизирует блокировку для синхронизации доступа к объекту из нескольких потоков.  При построении он приобретает замок и при уничтожении он выпускает замок.

## <a name="syntax"></a>Синтаксис

```cpp
ref class lock;
```

## <a name="remarks"></a>Remarks

`lock`доступен только для объектов CLR и может использоваться только в коде CLR.

Внутренне класс блокировки <xref:System.Threading.Monitor> используется для синхронизации доступа. Для получения дополнительной информации смотрите ссылки на статью.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|---------|-----------|
|[lock::lock](#lock)|Строит `lock` объект, дополнительно ожидая, чтобы приобрести замок навсегда, в течение определенного количества времени, или не на всех.|
|[блокировка:::блокировка](#tilde-lock)|Уничтожает `lock` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|---------|-----------|
|[lock::acquire](#acquire)|Приобретает замок на объекте, дополнительно ожидая, чтобы приобрести блокировку навсегда, на определенное количество времени, или не на всех.|
|[lock::is_locked](#is-locked)|Указывает, удерживается ли блокировка.|
|[lock::release](#release)|Выпускает замок.|
|[lock::try_acquire](#try-acquire)|Приобретает блокировку на объекте, ожидая определенного времени `bool` и возвращая, чтобы сообщить об успехе приобретения вместо того, чтобы выбросить исключение.|

### <a name="public-operators"></a>Публичные операторы

|Имя|Описание|
|---------|-----------|
|[замок::оператор&nbsp;bool](#operator-bool)|Оператор для `lock` использования в условном выражении.|
|[lock::operator==](#operator-equality)|Оператор по вопросам равенства.|
|[блокировка::оператор!](#operator-inequality)|Оператор неравенства.|

## <a name="requirements"></a>Требования

**Файл** \<заголовка msclr-lock.h>

**Namespace** msclr

## <a name="locklock"></a><a name="lock"></a>замок::замок

Строит `lock` объект, дополнительно ожидая, чтобы приобрести замок навсегда, в течение определенного количества времени, или не на всех.

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

*_object*<br/>
Объект, который будет заблокирован.

*_timeout*<br/>
Время из значения в миллисекундах или в <xref:System.TimeSpan>качестве .

### <a name="exceptions"></a>Исключения

Броски, <xref:System.ApplicationException> если приобретение блокировки не происходит до тайм-аута.

### <a name="remarks"></a>Remarks

Первые три формы конструктора пытаются приобрести `_object` блокировку в течение <xref:System.Threading.Timeout.Infinite> указанного периода тайм-аута (или если ни одна не указана).

Четвертая форма конструктора не приобретает `_object`блокировку. `lock_later`является членом [lock_when enum](../dotnet/lock-when-enum.md). Используйте [блокировку::приобретение](../dotnet/lock-acquire.md) или [блокировка::try_acquire](../dotnet/lock-try-acquire.md) приобрести блокировку в этом случае.

Блокировка будет автоматически выпущена при вызове деструктора.

`_object`не может <xref:System.Threading.ReaderWriterLock>быть .  Если это так, то выведется ошибка компилятора.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках. Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки. Затем основное приложение ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение своих задач.

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

## <a name="locklock"></a><a name="tilde-lock"></a>блокировка:::блокировка

Уничтожает `lock` объект.

```cpp
~lock();
```

### <a name="remarks"></a>Remarks

Деструктор вызывает [блокировку::release](../dotnet/lock-release.md).

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока.  Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки. Затем основное приложение ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение своих задач.

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

## <a name="lockacquire"></a><a name="acquire"></a>блокировка::приобретение

Приобретает замок на объекте, дополнительно ожидая, чтобы приобрести блокировку навсегда, на определенное количество времени, или не на всех.

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
Значение тайм-аута в <xref:System.TimeSpan>миллисекундах или в виде .

### <a name="exceptions"></a>Исключения

Броски, <xref:System.ApplicationException> если приобретение блокировки не происходит до тайм-аута.

### <a name="remarks"></a>Remarks

Если значение тайм-аута не поставляется, тайм-аут по умолчанию <xref:System.Threading.Timeout.Infinite>.

Если блокировка уже приобретена, эта функция ничего не делает.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки. Затем основное приложение ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение своих задач.

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

## <a name="lockis_locked"></a><a name="is-locked"></a>замок::is_locked

Указывает, удерживается ли блокировка.

```cpp
bool is_locked();
```

### <a name="return-value"></a>Возвращаемое значение

`true`если замок удерживается, `false` в противном случае.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока.  Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки, и ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение задач.

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

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>замок::оператор bool

Оператор для `lock` использования в условном выражении.

```cpp
operator bool();
```

### <a name="return-value"></a>Возвращаемое значение

`true`если замок удерживается, `false` в противном случае.

### <a name="remarks"></a>Remarks

Этот оператор фактически `_detail_class::_safe_bool` преобразует, к `bool` которому безопаснее, чем потому, что он не может быть преобразован в интегральный тип.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках.  Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки. Основное приложение ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение своих задач.

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

## <a name="lockrelease"></a><a name="release"></a>блокировка::освобождение

Выпускает замок.

```cpp
void release();
```

### <a name="remarks"></a>Remarks

Если блокировка не `release` удерживается, ничего не делает.

Вы не должны вызывать эту функцию явно. Когда `lock` объект выходит за рамки, его деструктор вызывает. `release`

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках. Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки. Затем основное приложение ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение своих задач.

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

## <a name="locktry_acquire"></a><a name="try-acquire"></a>замок::try_acquire

Приобретает блокировку на объекте, ожидая определенного времени `bool` и возвращая, чтобы сообщить об успехе приобретения вместо того, чтобы выбросить исключение.

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
Значение тайм-аута в <xref:System.TimeSpan>миллисекундах или в виде .

### <a name="return-value"></a>Возвращаемое значение

`true`если блокировка `false` была приобретена, в противном случае.

### <a name="remarks"></a>Remarks

Если блокировка уже приобретена, эта функция ничего не делает.

### <a name="example"></a>Пример

В этом примере используется один экземпляр класса в нескольких потоках. Класс использует блокировку, чтобы убедиться, что доступ к его внутренним данным является последовательным для каждого потока. Основной поток приложения использует блокировку на том же экземпляре класса, чтобы периодически проверять, существуют ли рабочие потоки. Затем основное приложение ждет выхода до тех пор, пока все рабочие потоки не завершат выполнение своих задач.

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

## <a name="lockoperator"></a><a name="operator-equality"></a>блокировка::оператор

Оператор по вопросам равенства.

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Объект для сравнения на равенство.

### <a name="return-value"></a>Возвращаемое значение

`true` Возвращает, `t` если он такой же, `false` как объект блокировки, в противном случае.

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

## <a name="lockoperator"></a><a name="operator-inequality"></a>блокировка::оператор!

Оператор неравенства.

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Объект для сравнения для неравенства.

### <a name="return-value"></a>Возвращаемое значение

`true` Возвращает, `t` если отличается от объекта `false` блокировки, в противном случае.

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
