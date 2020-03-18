---
title: Предложения OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- if
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 92bd73fda5891b0bbf7393d1a7fda573d0f00263
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424161"
---
# <a name="openmp-clauses"></a>Предложения OpenMP

Предоставляет ссылки на предложения, используемые в API OpenMP.

Визуальный C++ элемент поддерживает следующие предложения OpenMP.

Для общих атрибутов:

|Предложение|Description|
|------|-----------|
|[if](#if-openmp) (если);|Указывает, должен ли цикл выполняться параллельно или последовательно.|
|[num_threads](#num-threads)|Задает число потоков в команде потока.|
|[упорядоченный](#ordered-openmp-clauses)|Требуется для параллельной инструкции [for](openmp-directives.md#for-openmp) , если [упорядоченная](openmp-directives.md#ordered-openmp-directives) директива должна использоваться в цикле.|
|[schedule](#schedule)|Применяется к директиве [for](openmp-directives.md#for-openmp) .|
|[nowait](#nowait)|Переопределяет барьер, неявный в директиве.|

Для атрибутов совместного использования данных:

|Предложение|Description|
|------|-----------|
|[private](#private-openmp)|Указывает, что каждый поток должен иметь собственный экземпляр переменной.|
|[firstprivate](#firstprivate)|Указывает, что каждый поток должен иметь собственный экземпляр переменной и что переменная должна инициализироваться значением переменной, поскольку она существует до параллельной конструкции.|
|[lastprivate](#lastprivate)|Указывает, что версия переменной включающего контекста установлена равна закрытой версии любого потока, выполняющего окончательную итерацию (конструкцию цикла for) или в последнем разделе (#pragma разделов).|
|[используемый](#shared-openmp)|Указывает, что одна или несколько переменных должны быть общими для всех потоков.|
|[значение по умолчанию](#default-openmp)|Задает поведение неограниченных переменных в параллельной области.|
|[reduction](#reduction)|Указывает, что одна или несколько переменных, являющихся частными для каждого потока, являются субъектом операции сокращения в конце параллельной области.|
|[copyin](#copyin)|Разрешает потокам получать доступ к значению главного потока для переменной [threadprivate](openmp-directives.md#threadprivate) .|
|[copyprivate](#copyprivate)|Указывает, что одна или несколько переменных должны быть общими для всех потоков.|

## <a name="copyin"></a>copyin

Разрешает потокам получать доступ к значению главного потока для переменной [threadprivate](openmp-directives.md#threadprivate) .

```cpp
copyin(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Переменная `threadprivate`, которая будет инициализирована значением переменной в главном потоке, как оно существует до параллельной конструкции.

### <a name="remarks"></a>Remarks

`copyin` применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2.7.2.7 Copying](../../../parallel/openmp/2-7-2-7-copyin.md).

### <a name="example"></a>Пример

Пример использования `copyin`см. в разделе [threadprivate](openmp-directives.md#threadprivate) .

## <a name="copyprivate"></a>copyprivate

Указывает, что одна или несколько переменных должны быть общими для всех потоков.

```cpp
copyprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Одна или несколько переменных для совместного использования. Если указано более одной переменной, имена переменных следует разделять запятыми.

### <a name="remarks"></a>Remarks

`copyprivate` применяется к директиве [Single](openmp-directives.md#single) .

Дополнительные сведения см. в разделе [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md).

### <a name="example"></a>Пример

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default-openmp"></a>параметры

Задает поведение неограниченных переменных в параллельной области.

```cpp
default(shared | none)
```

### <a name="remarks"></a>Remarks

`shared`, которая действует, если предложение `default` не задано, означает, что любая переменная в параллельной области будет обрабатываться так, как если бы она была указана в предложении [Shared](#shared-openmp) . `none` означает, что любая переменная, используемая в параллельной области, не относящейся к предложению [Private](#private-openmp), [Shared](#shared-openmp), [reduction](#reduction), [фирстпривате](#firstprivate)или [lastprivate](#lastprivate) , вызовет ошибку компилятора.

`default` применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2.7.2.5 Default](../../../parallel/openmp/2-7-2-5-default.md).

### <a name="example"></a>Пример

Пример использования `default`см. в разделе [Private](#private-openmp) .

## <a name="firstprivate"></a>фирстпривате

Указывает, что каждый поток должен иметь собственный экземпляр переменной и что переменная должна инициализироваться значением переменной, поскольку она существует до параллельной конструкции.

```cpp
firstprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Переменная для создания экземпляров в каждом потоке, которая будет инициализирована значением переменной, так как она существует до параллельной конструкции. Если указано более одной переменной, имена переменных следует разделять запятыми.

### <a name="remarks"></a>Remarks

`firstprivate` применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [священ](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Дополнительные сведения см. в разделе [2.7.2.2 фирстпривате](../../../parallel/openmp/2-7-2-2-firstprivate.md).

### <a name="example"></a>Пример

Пример использования `firstprivate`см. в примере в разделе [Private](#private-openmp).

## <a name="if-openmp"></a>Если (OpenMP)

Указывает, должен ли цикл выполняться параллельно или последовательно.

```cpp
if(expression)
```

### <a name="parameters"></a>Параметры

*expression*<br/>
Целочисленное выражение, которое, если оно имеет значение true (отличное от нуля), приводит к параллельному выполнению кода в параллельной области. Если результат вычисления выражения равен false (нулю), то параллельная область выполняется в последовательном (отдельном потоке).

### <a name="remarks"></a>Remarks

`if` применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2,3 Parallel конструкции](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Пример

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a>lastprivate

Указывает, что версия переменной включающего контекста установлена равна закрытой версии любого потока, выполняющего окончательную итерацию (конструкцию цикла for) или в последнем разделе (#pragma разделов).

```cpp
lastprivate(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Переменная, которая установлена равна закрытой версии любого потока, выполняет окончательную итерацию (конструкцию цикла for) или последний раздел (#pragma разделов).

### <a name="remarks"></a>Remarks

`lastprivate` применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).

### <a name="example"></a>Пример

Пример использования предложения `lastprivate` см. в разделе [Расписание](#schedule) .

## <a name="nowait"></a>nowait

Переопределяет барьер, неявный в директиве.

```cpp
nowait
```

### <a name="remarks"></a>Remarks

`nowait` применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Дополнительные сведения см. в разделах [2.4.1 for конструировать](../../../parallel/openmp/2-4-1-for-construct.md), [2.4.2 Sections конструкции](../../../parallel/openmp/2-4-2-sections-construct.md)и [2.4.3 Single конструкции](../../../parallel/openmp/2-4-3-single-construct.md).

### <a name="example"></a>Пример

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num-threads"></a>num_threads

Задает число потоков в команде потока.

```cpp
num_threads(num)
```

### <a name="parameters"></a>Параметры

*num*<br/>
Число потоков

### <a name="remarks"></a>Remarks

Предложение `num_threads` имеет те же функциональные возможности, что и функция [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) .

`num_threads` применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2,3 Parallel конструкции](../../../parallel/openmp/2-3-parallel-construct.md).

### <a name="example"></a>Пример

Пример использования предложения `num_threads` см. в разделе [Parallel](openmp-directives.md#parallel) .

## <a name="ordered-openmp-clauses"></a>упорядоченный

Требуется для параллельной инструкции [for](openmp-directives.md#for-openmp) , если [упорядоченная](openmp-directives.md#ordered-openmp-directives) директива должна использоваться в цикле.

```cpp
ordered
```

### <a name="remarks"></a>Remarks

`ordered` применяется к директиве [for](openmp-directives.md#for-openmp) .

Дополнительные сведения см. в разделе [2.4.1 for конструировать](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Пример

Пример использования предложения `ordered` см. в разделе [ordered](openmp-directives.md#ordered-openmp-directives) .

## <a name="private-openmp"></a>личному

Указывает, что каждый поток должен иметь собственный экземпляр переменной.

```cpp
private(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Переменная, в которой имеются экземпляры в каждом потоке.

### <a name="remarks"></a>Remarks

`private` применяется к следующим директивам:

- [for](openmp-directives.md#for-openmp)
- [parallel](openmp-directives.md#parallel)
- [священ](openmp-directives.md#sections-openmp)
- [single](openmp-directives.md#single)

Дополнительные сведения см. в разделе [2.7.2.1 Private](../../../parallel/openmp/2-7-2-1-private.md).

### <a name="example"></a>Пример

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a>снизить

Указывает, что одна или несколько переменных, являющихся частными для каждого потока, являются субъектом операции сокращения в конце параллельной области.

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>Параметры

*operation*<br/>
Оператор для операции с переменными *var* в конце параллельной области.

*var*<br/>
Одна или несколько переменных, для которых необходимо выполнить скалярное сокращение. Если указано более одной переменной, имена переменных следует разделять запятыми.

### <a name="remarks"></a>Remarks

`reduction` применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2.7.2.6 reduction](../../../parallel/openmp/2-7-2-6-reduction.md).

### <a name="example"></a>Пример

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a>Расписание

Применяется к директиве [for](openmp-directives.md#for-openmp) .

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>Параметры

*type*<br/>
Тип расписания: `dynamic`, `guided`, `runtime`или `static`.

*size*<br/>
Используемых Задает размер итераций. *Размер* должен быть целым числом. Недопустимо, если *тип* — `runtime`.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [2.4.1 for конструировать](../../../parallel/openmp/2-4-1-for-construct.md).

### <a name="example"></a>Пример

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared-openmp"></a>используемый

Указывает, что одна или несколько переменных должны быть общими для всех потоков.

```cpp
shared(var)
```

### <a name="parameters"></a>Параметры

*var*<br/>
Одна или несколько переменных для совместного использования. Если указано более одной переменной, имена переменных следует разделять запятыми.

### <a name="remarks"></a>Remarks

Другим способом совместного использования переменных в потоках является предложение [copyprivate](#copyprivate) .

`shared` применяется к следующим директивам:

- [parallel](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [священ](openmp-directives.md#sections-openmp)

Дополнительные сведения см. в разделе [2.7.2.4 Shared](../../../parallel/openmp/2-7-2-4-shared.md).

### <a name="example"></a>Пример

Пример использования `shared`см. в разделе [Private](#private-openmp) .
