---
title: Директивы OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP directives
- atomic
- barrier
- critical
- flush
- for
- master
- ordered
- parallel
- section
- SECTIONS
- single
- threadprivate
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98fec6659c2f4e998b946983a0bd2bdea6d0cde1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083260"
---
# <a name="openmp-directives"></a>Директивы OpenMP

Ссылки на директивы, используемые в OpenMP API.

Visual C++ поддерживает следующие директивы OpenMP.

|Директива|Описание|
|---------|-----------|
|[atomic](#atomic)|Указывает, что ячейку памяти, которая обновляется атомарно.|
|[barrier](#barrier)|Синхронизирует все потоки в группе; все потоки остановиться барьера, пока все потоки выполнения барьера.|
|[critical](#critical)|Указывает, что код только выполняется в одном потоке за раз.|
|[flush](#flush-openmp)|Указывает, что все потоки имеют одинаковое представление памяти для всех общих объектов.|
|[for](#for-openmp)|Приводит к работе, выполненной в `for` цикла внутри параллельной области для будет разделен между потоками.|
|[master](#master)|Указывает, что только главный поток должен выполняться части программы.|
|[Упорядоченные](#ordered-openmp-directives)|Код в разделе распараллеленное `for` цикл должен выполняться как последовательный цикл.|
|[parallel](#parallel)|Определяет параллельной области, который приведен код, который будет выполняться сразу несколько потоков параллельно.|
|[Разделы](#sections-openmp)|Идентифицирует разделов кода необходимо распределить между всеми потоками.|
|[single](#single)|Позволяет указать, что раздела кода, должна выполняться в одном потоке, не обязательно главного потока.|
|[threadprivate](#threadprivate)|Указывает, что переменная является частной для потока.|

## <a name="atomic"></a>atomic

Указывает, что ячейку памяти, которая обновляется атомарно.

```
#pragma omp atomic
   expression
```

### <a name="parameters"></a>Параметры

*Выражение*<br/>
Инструкция, которая имеет lvalue, местоположением памяти, необходимо обеспечить защиту от более чем одной записи. Дополнительные сведения о формах допустимые выражения см. в спецификации OpenMP.

### <a name="remarks"></a>Примечания

`atomic` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.6.4 atomic создания](../../../parallel/openmp/2-6-4-atomic-construct.md).

### <a name="example"></a>Пример

```
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

## <a name="barrier"></a>Барьер

Синхронизирует все потоки в группе; все потоки остановиться барьера, пока все потоки выполнения барьера.

```
#pragma omp barrier
```

### <a name="remarks"></a>Примечания

`barrier` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.6.3 директива barrier](../../../parallel/openmp/2-6-3-barrier-directive.md).

### <a name="example"></a>Пример

Пример использования `barrier`, см. в разделе [master](#master).

## <a name="critical"></a>Критические

Указывает, что код будет выполняться только в одном потоке за раз.

```
#pragma omp critical [(name)]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*name*<br/>
(Необязательно) Имя для идентификации кода уровня critical. Обратите внимание, что это имя должно заключаться в круглые скобки.

### <a name="remarks"></a>Примечания

`critical` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.6.2 критических создания](../../../parallel/openmp/2-6-2-critical-construct.md).

### <a name="example"></a>Пример

```
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

## <a name="flush-openmp"></a>Flush (OpenMP)

Указывает, что все потоки имеют одинаковое представление памяти для всех общих объектов.

```
#pragma omp flush [(var)]
```

### <a name="parameters"></a>Параметры

*var*<br/>
(Необязательно) Разделенный запятыми список переменных, которые представляют объекты, которые требуется синхронизировать. Если `var` не указан, вся память очищается.

### <a name="remarks"></a>Примечания

`flush` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.6.5 директива flush](../../../parallel/openmp/2-6-5-flush-directive.md).

### <a name="example"></a>Пример

```
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

## <a name="for-openmp"></a>для (OpenMP)

Приводит к работе, выполненной в `for` цикла внутри параллельной области для будет разделен между потоками.

```
#pragma omp [parallel] for [clauses]
   for_statement
```

### <a name="parameters"></a>Параметры

*Предложения*<br/>
(Необязательно) Ноль или несколько предложений. См. в разделе "Примечания" для получения списка предложений, поддерживаемые `for`.

*for_statement*<br/>
Объект `for` цикла. Приведет к неопределенному поведению, если код пользователя в `for` цикла изменяется переменная индекса.

### <a name="remarks"></a>Примечания

`for` Директива поддерживает следующие предложения OpenMP:

- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [nowait](openmp-clauses.md#nowait)
- [Упорядоченные](openmp-clauses.md#ordered-openmp-clauses)
- [private](openmp-clauses.md#private-openmp)
- [reduction](openmp-clauses.md#reduction)
- [schedule](openmp-clauses.md#schedule)

Если `parallel` также указан `clauses` предложения принимаются по `parallel` или `for` директивы, за исключением `nowait`.

Дополнительные сведения см. в разделе [2.4.1 конструкция for](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Пример

```
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

## <a name="master"></a>Master

Указывает, что только главный поток должен выполняться части программы.

```
#pragma omp master
{
   code_block
}
```

### <a name="remarks"></a>Примечания

`master` Директива поддерживает без предложения OpenMP.

[Единый](#single) директива позволяет указать, что раздела кода, должна выполняться в одном потоке, не обязательно главного потока.

Дополнительные сведения см. в разделе [2.6.1 master конструкция](../../../parallel/openmp/2-6-1-master-construct.md).

### <a name="example"></a>Пример

```
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

## <a name="ordered-openmp-directives"></a>ORDERED (директивы OpenMP)

Код в разделе распараллеленное `for` цикл должен выполняться как последовательный цикл.

```
#pragma omp ordered
   structured-block
```

### <a name="remarks"></a>Примечания

`ordered` Директива должна быть в пределах динамический объем [для](#for-openmp) или `parallel for` построения с `ordered` предложение.

`ordered` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.6.6 конструкция ordered](../../../parallel/openmp/2-6-6-ordered-construct.md).

### <a name="example"></a>Пример

```
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

## <a name="parallel"></a>Параллельный

Определяет параллельной области, который приведен код, который будет выполняться сразу несколько потоков параллельно.

```
#pragma omp parallel [clauses]
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*Предложения*<br/>
(Необязательно) Ноль или несколько предложений.  См. в разделе "Примечания" для получения списка предложений, поддерживаемые `parallel`.

### <a name="remarks"></a>Примечания

`parallel` Директива поддерживает следующие предложения OpenMP:

- [copyin](openmp-clauses.md#copyin)
- [default](openmp-clauses.md#default-openmp)
- [firstprivate](openmp-clauses.md#firstprivate)
- [if](openmp-clauses.md#if-openmp)
- [num_threads](openmp-clauses.md#num-threads)
- [private](openmp-clauses.md#private-openmp)
- [reduction](openmp-clauses.md#reduction)
- [Общие](openmp-clauses.md#shared-openmp)

`parallel` Можно также использовать с [разделах](#sections-openmp) и [для](#for-openmp) директивы.

Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Пример

Следующий пример показано, как настроить количество потоков и определить область параллельной обработки. Количество потоков равно по умолчанию число логических процессоров на компьютере. Например если машины с одним физическим процессором с поддержкой технологии Hyper-Threading, он будет иметь двух логических процессоров и двумя потоками.

```
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

### <a name="comment"></a>Комментарий

Обратите внимание, что порядок выходных данных могут различаться на разных компьютерах.

## <a name="sections-openmp"></a>разделы (OpenMP)

Идентифицирует разделов кода необходимо распределить между всеми потоками.

```
#pragma omp [parallel] sections [clauses]
{
   #pragma omp section
   {
      code_block
   } 
}
```

### <a name="parameters"></a>Параметры

*Предложения*<br/>
(Необязательно) Ноль или несколько предложений. См. в разделе "Примечания" для получения списка предложений, поддерживаемые `sections`.

### <a name="remarks"></a>Примечания

`sections` Директива может содержать ноль или более `section` директивы.

`sections` Директива поддерживает следующие предложения OpenMP:

- [firstprivate](openmp-clauses.md#firstprivate)
- [lastprivate](openmp-clauses.md#lastprivate)
- [nowait](openmp-clauses.md#nowait)
- [private](openmp-clauses.md#private-openmp)
- [reduction](openmp-clauses.md#reduction)

Если `parallel` также указан `clauses` предложения принимаются по `parallel` или `sections` директивы, за исключением `nowait`.

Дополнительные сведения см. в разделе [2.4.2 конструкция sections](../../../parallel/openmp/2-4-2-sections-construct.md).

### <a name="example"></a>Пример

```
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

## <a name="single"></a>Единый

Позволяет указать, что раздела кода, должна выполняться в одном потоке, не обязательно главного потока.

```
#pragma omp single [clauses] 
{
   code_block
}
```

### <a name="parameters"></a>Параметры

*Предложения*<br/>
(Необязательно) Ноль или несколько предложений. См. в разделе "Примечания" для получения списка предложений, поддерживаемые `single`.

### <a name="remarks"></a>Примечания

`single` Директива поддерживает следующие предложения OpenMP:

- [copyprivate](openmp-clauses.md#copyprivate)
- [firstprivate](openmp-clauses.md#firstprivate)
- [nowait](openmp-clauses.md#nowait)
- [private](openmp-clauses.md#private-openmp)

[Master](#master) директива позволяет указать, что раздела кода, должны выполняться только для главного потока.

Дополнительные сведения см. в разделе [создать единый 2.4.3](../../../parallel/openmp/2-4-3-single-construct.md).

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

## <a name="threadprivate"></a>threadprivate

Указывает, что переменная является частной для потока.

```
#pragma omp threadprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Разделенный запятыми список переменных, которые вы хотите сделать частными потоку. `var` должен быть переменной глобального - или действующую в пространстве имен или статической локальной переменной.

### <a name="remarks"></a>Примечания

`threadprivate` Директива поддерживает без предложения OpenMP.

Дополнительные сведения см. в разделе [2.7.1 директива threadprivate](../../../parallel/openmp/2-7-1-threadprivate-directive.md).

`threadprivate` Директива основан на [поток](../../../cpp/thread.md) атрибуте с помощью [__declspec](../../../cpp/declspec.md) ключевое слово; ограничения на `__declspec(thread)` применяются к `threadprivate`.

Нельзя использовать `threadprivate` в любой библиотеки DLL, которые будут загружены через [LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya).  Этот запрет включает библиотек DLL, загружаемых с [/DELAYLOAD (Импорт отложенной загрузки)](../../../build/reference/delayload-delay-load-import.md), который также используется `LoadLibrary`.

Можно использовать `threadprivate` в библиотеку DLL, которая загружается статически при запуске процесса.

Так как `threadprivate` основан на `__declspec(thread)`, `threadprivate` переменной будет существовать в любом потоке, в процессе работы не только эти потоки, которые являются частью группы потоков, сформированными параллельной области.  Имейте в виду часть подробностей этой реализации; Вы можете заметить, например, что конструкторы для `threadprivate` определяемого пользователем типа, называются дополнительные чаще, чем ожидалось.

Объект `threadprivate` переменной destructable типа не гарантируется его деструктор вызывается.  Пример:

```
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

Пользователи не имеют контроля о том, когда прекращается при обнаружении потоков, образующей область параллельной обработки.  Если при завершении процесса, потоки не будут высылаться уведомления о выходе процесса и деструктор не будет вызываться для существует этих потоков `threaded_var` в любом потоке, за исключением того, который завершает работу (в данном случае — основной поток).  Чтобы код не следует полагаться на правильное уничтожение `threadprivate` переменные.

### <a name="example"></a>Пример

Пример использования `threadprivate`, см. в разделе [частного](openmp-clauses.md#private-openmp).
