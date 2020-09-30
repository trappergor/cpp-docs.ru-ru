---
title: Директивы OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- parallel
- section
- single
- threadprivate
helpviewer_keywords:
- OpenMP directives
- atomic OpenMP directive
- barrier OpenMP directive
- critical OpenMP directive
- flush OpenMP directive
- for OpenMP directive
- master OpenMP directive
- ordered OpenMP directive
- parallel OpenMP directive
- sections OpenMP directive
- single OpenMP directive
- threadprivate OpenMP directive
ms.assetid: 0562c263-344c-466d-843e-de830d918940
ms.openlocfilehash: 21270e8cdeb17b6d06d903d328962435c627759f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503824"
---
# <a name="openmp-directives"></a>Директивы OpenMP

Предоставляет ссылки на директивы, используемые в API OpenMP.

Visual C++ поддерживает следующие директивы OpenMP.

Для параллельного совместного использования:

|Директива|Описание|
|---------|-----------|
|[распараллеливани](#parallel)|Определяет параллельную область, которая является кодом, который будет выполняться несколькими потоками параллельно.|
|[for](#for-openmp)|Приводит к тому, что работа, выполненная в `for` цикле внутри параллельной области, делится между потоками.|
|[священ](#sections-openmp)|Определяет разделы кода, которые должны быть разделены между всеми потоками.|
|[single](#single)|Позволяет указать, что раздел кода должен выполняться в одном потоке, а не в главном потоке.|

Для главной и синхронизации:

|Директива|Описание|
|---------|-----------|
|[master](#master)|Указывает, что только главный поток должен выполнить раздел программы.|
|[критическое](#critical)|Указывает, что код выполняется только в одном потоке за раз.|
|[лежащим](#barrier)|Синхронизирует все потоки в команде; все потоки приостанавливаются в барьере, пока все потоки не будут выполнять барьер.|
|[at](#atomic)|Указывает, что область памяти, которая будет обновляться атомарно.|
|[flush](#flush-openmp)|Указывает, что все потоки имеют одинаковое представление памяти для всех общих объектов.|
|[упорядоченный](#ordered-openmp-directives)|Указывает, что код в параллельном `for` цикле должен выполняться как последовательный цикл.|

Для среды данных:

|Директива|Описание|
|---------|-----------|
|[threadprivate](#threadprivate)|Указывает, что переменная является закрытой для потока.|

## <a name="atomic"></a><a name="atomic"></a> at

Указывает, что область памяти, которая будет обновляться атомарно.

```cpp
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Инструкция с *левосторонним*значением, расположение памяти которого необходимо защитить от более чем одной записи.

### <a name="remarks"></a>Remarks

`atomic`Директива не поддерживает никаких предложений.

Дополнительные сведения см. в разделе [2.6.4 Atomic конструкции](../2-directives.md#264-atomic-construct).

### <a name="example"></a>Пример

```cpp
// omp_atomic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define MAX 10

int main() {
   int count = 0;
   #pragma omp parallel num_threads(MAX)
   {
      #pragma omp atomic
      count++;
   }
   printf_s("Number of threads: %d\n", count);
}
```

```Output
Number of threads: 10
```

## <a name="barrier"></a><a name="barrier"></a> лежащим

Синхронизирует все потоки в команде; все потоки приостанавливаются в барьере, пока все потоки не будут выполнять барьер.

```cpp
#pragma omp barrier
```

### <a name="remarks"></a>Remarks

`barrier`Директива не поддерживает никаких предложений.

Дополнительные сведения см. в разделе [Директива 2.6.3 барьера](../2-directives.md#263-barrier-directive).

### <a name="example"></a>Пример

Пример использования см `barrier` . в разделе [master](#master).

## <a name="critical"></a><a name="critical"></a> критическое

Указывает, что код должен выполняться только в одном потоке за раз.

```cpp
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*name*<br/>
Используемых Имя для поиска критического кода. Имя должно быть заключено в круглые скобки.

### <a name="remarks"></a>Remarks

`critical`Директива не поддерживает никаких предложений.

Дополнительные сведения см. в разделе [2.6.2 Критическая конструкция](../2-directives.md#262-critical-construct).

### <a name="example"></a>Пример

```cpp
// omp_critical.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10

int main()
{
    int i;
    int max;
    int a[SIZE];

    for (i = 0; i < SIZE; i++)
    {
        a[i] = rand();
        printf_s("%d\n", a[i]);
    }

    max = a[0];
    #pragma omp parallel for num_threads(4)
        for (i = 1; i < SIZE; i++)
        {
            if (a[i] > max)
            {
                #pragma omp critical
                {
                    // compare a[i] and max again because max
                    // could have been changed by another thread after
                    // the comparison outside the critical section
                    if (a[i] > max)
                        max = a[i];
                }
            }
        }

    printf_s("max = %d\n", max);
}
```

```Output
41
18467
6334
26500
19169
15724
11478
29358
26962
24464
max = 29358
```

## <a name="flush"></a><a name="flush-openmp"></a> идет

Указывает, что все потоки имеют одинаковое представление памяти для всех общих объектов.

```cpp
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Параметры

*var*<br/>
Используемых Разделенный запятыми список переменных, представляющих объекты, которые необходимо синхронизировать. Если *переменная var* не указана, вся память очищается.

### <a name="remarks"></a>Remarks

`flush`Директива не поддерживает никаких предложений.

Дополнительные сведения см. в описании [директивы 2.6.5 Flush](../2-directives.md#265-flush-directive).

### <a name="example"></a>Пример

```cpp
// omp_flush.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void read(int *data) {
   printf_s("read data\n");
   *data = 1;
}

void process(int *data) {
   printf_s("process data\n");
   (*data)++;
}

int main() {
   int data;
   int flag;

   flag = 0;

   #pragma omp parallel sections num_threads(2)
   {
      #pragma omp section
      {
         printf_s("Thread %d: ", omp_get_thread_num( ));
         read(&data);
         #pragma omp flush(data)
         flag = 1;
         #pragma omp flush(flag)
         // Do more work.
      }

      #pragma omp section
      {
         while (!flag) {
            #pragma omp flush(flag)
         }
         #pragma omp flush(data)

         printf_s("Thread %d: ", omp_get_thread_num( ));
         process(&data);
         printf_s("data = %d\n", data);
      }
   }
}
```

```Output
Thread 0: read data
Thread 1: process data
data = 2
```

## <a name="for"></a><a name="for-openmp"></a> предмет

Приводит к тому, что работа, выполненная в `for` цикле внутри параллельной области, делится между потоками.

```cpp
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Параметры

*предложения*<br/>
Используемых Ноль или более предложений, см. раздел **"Примечания** ".

*for_statement*<br/>
`for`Цикл. Неопределенное поведение будет вызвано тем, что пользовательский код в `for` цикле изменяет переменную индекса.

### <a name="remarks"></a>Remarks

`for`Директива поддерживает следующие предложения:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [снизить](openmp-clauses.md#reduction)
- [упорядоченный](openmp-clauses.md#ordered-openmp-clauses)
- [Расписание](openmp-clauses.md#schedule)
- [nowait](openmp-clauses.md#nowait)

Если `parallel` также указан параметр, `clauses` может быть любым предложением, которое `parallel` принимает `for` директивы или, за исключением `nowait` .

Дополнительные сведения см. в разделе [2.4.1 for конструировать](../2-directives.md#241-for-construct).

### <a name="example"></a>Пример

```cpp
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="master"></a><a name="master"></a> Master

Указывает, что только главный поток должен выполнить раздел программы.

```cpp
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Remarks

`master`Директива не поддерживает никаких предложений.

[Единственная](#single) директива позволяет указать, что раздел кода должен выполняться в одном потоке, а не в главном потоке.

Дополнительные сведения см. в статье [Главная конструкция 2.6.1](../2-directives.md#261-master-construct).

### <a name="example"></a>Пример

```cpp
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="ordered"></a><a name="ordered-openmp-directives"></a> упорядоченный

Указывает, что код в параллельном `for` цикле должен выполняться как последовательный цикл.

```cpp
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Remarks

`ordered`Директива должна находиться в динамической области конструкции [for](#for-openmp) или `parallel for` с `ordered` предложением.

`ordered`Директива не поддерживает никаких предложений.

Дополнительные сведения см. в разделе [2.6.6 Ordering конструкции](../2-directives.md#266-ordered-construct).

### <a name="example"></a>Пример

```cpp
// omp_ordered.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

static float a[1000], b[1000], c[1000];

void test(int first, int last)
{
    #pragma omp for schedule(static) ordered
    for (int i = first; i <= last; ++i) {
        // Do something here.
        if (i % 2)
        {
            #pragma omp ordered
            printf_s("test() iteration %d\n", i);
        }
    }
}

void test2(int iter)
{
    #pragma omp ordered
    printf_s("test2() iteration %d\n", iter);
}

int main( )
{
    int i;
    #pragma omp parallel
    {
        test(1, 8);
        #pragma omp for ordered
        for (i = 0 ; i < 5 ; i++)
            test2(i);
    }
}
```

```Output
test() iteration 1
test() iteration 3
test() iteration 5
test() iteration 7
test2() iteration 0
test2() iteration 1
test2() iteration 2
test2() iteration 3
test2() iteration 4
```

## <a name="parallel"></a><a name="parallel"></a> распараллеливани

Определяет параллельную область, которая является кодом, который будет выполняться несколькими потоками параллельно.

```cpp
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*предложения*<br/>
Используемых Ноль или более предложений, см. раздел **"Примечания** ".

### <a name="remarks"></a>Remarks

`parallel`Директива поддерживает следующие предложения:

- [if](openmp-clauses.md#if-openmp) (если);
- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [default](openmp-clauses.md#default-openmp)
- [используемый](openmp-clauses.md#shared-openmp)
- [copyin](openmp-clauses.md#copyin)
- [снизить](openmp-clauses.md#reduction)
- [num_threads](openmp-clauses.md#num-threads)

`parallel` также можно использовать с директивами [for](#for-openmp) и [Sections](#sections-openmp) .

Дополнительные сведения см. в разделе [2,3 Parallel конструкции](../2-directives.md#23-parallel-construct).

### <a name="example"></a>Пример

В следующем примере показано, как задать количество потоков и определить параллельную область. Число потоков равно количеству логических процессоров на компьютере по умолчанию. Например, если у вас есть компьютер с одним физическим процессором с включенной технологией Hyper-Threading, у него будет два логических процессора и два потока. Порядок выходных данных может различаться на разных компьютерах.

```cpp
// omp_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(4)
   {
      int i = omp_get_thread_num();
      printf_s("Hello from thread %d\n", i);
   }
}
```

```Output
Hello from thread 0
Hello from thread 1
Hello from thread 2
Hello from thread 3
```

## <a name="sections"></a><a name="sections-openmp"></a> священ

Определяет разделы кода, которые должны быть разделены между всеми потоками.

```cpp
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   }
}
```

### <a name="parameters"></a>Параметры

*предложения*<br/>
Используемых Ноль или более предложений, см. раздел **"Примечания** ".

### <a name="remarks"></a>Remarks

`sections`Директива может содержать ноль или более `section` директив.

`sections`Директива поддерживает следующие предложения:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [снизить](openmp-clauses.md#reduction)
- [nowait](openmp-clauses.md#nowait)

Если `parallel` также указан параметр, `clauses` может быть любым предложением, которое `parallel` принимает `sections` директивы или, за исключением `nowait` .

Дополнительные сведения см. в разделе [2.4.2 Sections конструкции](../2-directives.md#242-sections-construct).

### <a name="example"></a>Пример

```cpp
// omp_sections.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
    #pragma omp parallel sections num_threads(4)
    {
        printf_s("Hello from thread %d\n", omp_get_thread_num());
        #pragma omp section
        printf_s("Hello from thread %d\n", omp_get_thread_num());
    }
}
```

```Output
Hello from thread 0
Hello from thread 0
```

## <a name="single"></a><a name="single"></a> один

Позволяет указать, что раздел кода должен выполняться в одном потоке, а не в главном потоке.

```cpp
#pragma omp single [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*предложения*<br/>
Используемых Ноль или более предложений, см. раздел **"Примечания** ".

### <a name="remarks"></a>Remarks

`single`Директива поддерживает следующие предложения:

- [private](openmp-clauses.md#private-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [copyprivate](openmp-clauses.md#copyprivate)
- [nowait](openmp-clauses.md#nowait)

[Основная](#master) директива позволяет указать, что раздел кода должен выполняться только в главном потоке.

Дополнительные сведения см. в разделе [2.4.3 Single конструкция](../2-directives.md#243-single-construct).

### <a name="example"></a>Пример

```cpp
// omp_single.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main() {
   #pragma omp parallel num_threads(2)
   {
      #pragma omp single
      // Only a single thread can read the input.
      printf_s("read input\n");

      // Multiple threads in the team compute the results.
      printf_s("compute results\n");

      #pragma omp single
      // Only a single thread can write the output.
      printf_s("write output\n");
    }
}
```

```Output
read input
compute results
compute results
write output
```

## <a name="threadprivate"></a><a name="threadprivate"></a> threadprivate

Указывает, что переменная является закрытой для потока.

```cpp
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Разделенный запятыми список переменных, которые необходимо сделать частными для потока. переменная *var* должна быть либо переменной с областью видимости глобального или пространства имен, либо локальной статической переменной.

### <a name="remarks"></a>Remarks

`threadprivate`Директива не поддерживает никаких предложений.

`threadprivate`Директива основана на атрибуте [Thread](../../../cpp/thread.md) , использующем ключевое слово [__declspec](../../../cpp/declspec.md) ; ограничения On `__declspec(thread)` применяются к `threadprivate` . Например, `threadprivate` переменная будет существовать в любом потоке, запущенном в процессе, а не только в потоках, которые являются частью группы потоков, порожденной параллельной областью. Учитывайте эти сведения о реализации; можно заметить, что конструкторы для `threadprivate` определяемого пользователем типа вызываются чаще, чем ожидается.

Можно использовать `threadprivate` в библиотеке DLL, которая статически загружается при запуске процесса, однако ее нельзя использовать `threadprivate` в любой библиотеке DLL, которая будет загружаться через [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw) , например библиотеки DLL, загруженные с помощью [параметр/DELAYLOAD (отложенная загрузка)](../../../build/reference/delayload-delay-load-import.md), которая также использует `LoadLibrary` .

`threadprivate`Для переменной типа *можно уничтожить* не гарантируется вызов деструктора. Пример:

```cpp
struct MyType
{
    ~MyType();
};

MyType threaded_var;
#pragma omp threadprivate(threaded_var)
int main()
{
    #pragma omp parallel
    {}
}
```

Пользователи не имеют контроля над тем, когда потоки, образующей параллельную область, будут завершаться. Если эти потоки существуют при завершении процесса, потоки не будут уведомлены о выходе процесса, а деструктор не будет вызываться для `threaded_var` любого потока, Кроме того, который завершается (здесь основной поток). Поэтому код не должен подсчитываться при правильном уничтожении `threadprivate` переменных.

Дополнительные сведения см. в разделе [2.7.1 threadprivate Directive](../2-directives.md#271-threadprivate-directive).

### <a name="example"></a>Пример

Пример использования см. в `threadprivate` разделе [Private](openmp-clauses.md#private-openmp).
