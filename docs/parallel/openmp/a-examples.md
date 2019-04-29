---
title: О. Примеры
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: 061490d34829175bfbdcd84d6208aa396bb19671
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362976"
---
# <a name="a-examples"></a>О. Примеры

Ниже приведены примеры конструкциями, определенными в этом документе. Оператору, следующему директиву комплексной, только при необходимости, а не составной оператор отображается с отступом относительно директиву предшествует ей.

## <a name="a1-a-simple-loop-in-parallel"></a>A.1 простой цикл в параллельном режиме

Следующий пример демонстрирует распараллелить цикл с помощью [параллельных для](2-directives.md#251-parallel-for-construct) директива. Переменная итерации цикла является закрытым по умолчанию, поэтому нет необходимости явно указывать в предложения private.

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>A.2 условной компиляции

Следующие примеры иллюстрируют использование условной компиляции, с помощью макроса OpenMP [_OPENMP](2-directives.md#22-conditional-compilation). При компиляции OpenMP `_OPENMP` становится определен макрос.

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Определенный Оператор препроцессора позволяет более чем один макрос для тестирования одну директиву.

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>A.3 параллельных регионов

[Параллельных](2-directives.md#23-parallel-construct) директива может использоваться в параллельных программах крупных фрагментов данных. В следующем примере каждый поток в параллельной области определяет, какая часть глобального массива `x` для работы, в зависимости от числа потоков:

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>A.4 предложения nowait

Если есть множество независимых циклы внутри параллельной области, можно использовать [nowait](2-directives.md#241-for-construct) предложение, чтобы избежать подразумеваемых барьера в конце `for` директивы, следующим образом:

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>A.5 директивы critical

Следующий пример содержит несколько [критических](2-directives.md#262-critical-construct) директивы. В примере показана модель организации очереди, в котором задачи удаляются из очереди и работали. Чтобы защититься от многих потоков выведении ту же задачу, операция удаления должна находиться в `critical` разделе. Две очереди в этом примере не зависят от, защищены ли они с `critical` директивы с разными именами *xaxis* и *ось y*.

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>A.6 предложения lastprivate

Иногда для правильного выполнения зависит от значения, последней итерации цикла присваивается переменной. Такие программы должен перечислить все такие переменные в качестве аргументов [lastprivate](2-directives.md#2723-lastprivate) предложение таким образом, значения переменных так же, как при выполнении цикла последовательно.

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

В предыдущем примере, значение `i` в конце параллельной области будут равны `n-1`, как показано в последовательном.

## <a name="a7-the-reduction-clause"></a>А.7 предложение reduction

В следующем примере демонстрируется [сокращения](2-directives.md#2726-reduction) предложение:

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>A.8 параллельных разделов

В следующем примере (для [разделе 2.4.2](2-directives.md#242-sections-construct)), функции *xaxis*, *ось y*, и *zaxis* могут быть выполнены одновременно. Первый `section` директива является необязательным.  Все `section` директивы должна отображаться в лексическую область `parallel sections` построения.

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>A.9 отдельных директив

В следующем примере демонстрируется [единый](2-directives.md#243-single-construct) директива. В примере, только один поток (обычно первый поток, у которых `single` директива) выводит сообщение о ходе выполнения. Пользователь не должен делать никаких предположений в каком потоке будет выполняться `single` раздел. Пропускает все прочие потоки `single` разделе и останавливать барьера в конце `single` построения. Если другие потоки могут продолжить работу без ожидания завершения потока, выполняющегося `single` разделе `nowait` предложение может быть указано в `single` директива.

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>A.10 последовательного упорядочивания

[Упорядоченные разделах](2-directives.md#266-ordered-construct) полезны для последовательное упорядочение в результате работы, выполняемой в параллельном режиме. Следующая программа выводит индексы в последовательном порядке:

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>A.11 объект фиксированное число потоков

Некоторые программы используют фиксированное, предопределенное число потоков для выполнения правильно.  Поскольку динамическую настройку количество потоков по умолчанию, определяемое реализацией, таких программ можно отключить возможность динамического потоков и задайте число потоков явным образом поддерживать переносимости. В следующем примере показано, как это сделать с помощью [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function), и [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function):

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

В этом примере программа работает правильно только в том случае, если он выполняется по 16 потоков. Если реализация не поддерживает 16 потоков, поведение в этом примере определяется реализацией.

Количество потоков, выполняющих параллельной области остается неизменной во время параллельной области, независимо от параметра динамические потоки. Механизм динамических потоков определяет число потоков, используемых в начале параллельной области и поддерживает постоянное до конца области.

## <a name="a12-the-atomic-directive"></a>A.12 директивы atomic

Следующий пример позволяет избежать состояния гонки (одновременное обновление элемента *x* много потоков) с помощью [atomic](2-directives.md#264-atomic-construct) директивы:

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Преимущество использования `atomic` директивы в этом примере является то, что обновление двух разных элементов x возникает в параллельном режиме. Если [критических](2-directives.md#262-critical-construct) директива используется вместо этого, а затем обновляет все элементы *x* выполняются последовательно (хотя в любом не гарантирует порядок).

`atomic` Команда применяется только для немедленно следующий за ним оператор C или C++.  В результате элементы *y* не обновляются атомарно, в этом примере.

## <a name="a13-a-flush-directive-with-a-list"></a>A.13 объект директивы flush со списком

В следующем примере используется `flush` директив для синхронизации точка-точка конкретных объектов между парами потоков:

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>A.14 объект директивы flush без списка

Следующий пример (для [разделе 2.6.5](2-directives.md#265-flush-directive)) отличает общих объектов, затронутых `flush` директиву без списка из общих объектов, которые не затрагиваются:

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>A.15 количества используемых потоков

Рассмотрим следующий пример неверные (для [раздел 3.1.2](3-run-time-library-functions.md#312-omp_get_num_threads-function)):

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()` Вызов возвращает значение 1 в последовательной раздела кода, поэтому *np* всегда будет равно 1 в предыдущем примере. Чтобы определить количество потоков, которые будут развернуты для параллельной области, внутри параллельной области должен быть вызов.

Приведенный ниже показано, как переписывать этой программы, не включая запрос для потоков:

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>A.16 блокировки

В следующем примере (для [разделе 3.2](3-run-time-library-functions.md#32-lock-functions)), аргумент для функции блокировки должен иметь тип `omp_lock_t`, и что нет необходимости в его очистка.  Функции блокировки вызвать потоки простаивать при ожидании записи для первого критический раздел, но может выполнять другие задачи во время ожидания для записи в секунду.  `omp_set_lock` Функция блоки, но `omp_test_lock` не функцию, что работа в `skip()` выполняться.

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>A.17 Вкладываемых блокировок

Следующий пример (для [разделе 3.2](3-run-time-library-functions.md#32-lock-functions)) демонстрируется использование вкладываемых блокировок для синхронизации обновлений для структуру в целом и для одного из его членов.

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>A.18 вложенные директивы for

В следующем примере `for` [директива nesting](2-directives.md#29-directive-nesting) является совместимым так как внутренний и внешний `for` директивы привязка к другой параллельных регионов:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

Следующий вариант предыдущего примера также является совместимым:

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19 примеры неправильного вложения совместной работы директив

В примерах этого раздела показаны [директива nesting](2-directives.md#29-directive-nesting) правила.

Следующий пример не соответствует требованиям из-за внутренней и внешней `for` директивы являются вложенными и привязать к тому же `parallel` директивы:

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

Следующая версия динамически вложенных в предыдущем примере также соответствует требованиям:

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

Следующий пример не соответствует требованиям поскольку `for` и `single` используются вложенные директивы, и их привязки к одной и той же параллельной области:

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

Следующий пример не соответствует требованиям поскольку `barrier` директив внутри `for` может вызвать взаимоблокировку:

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

Следующий пример не соответствует требованиям поскольку `barrier` приводит к взаимоблокировке тем, что только один поток за раз можно входить в критический раздел:

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

Следующий пример не соответствует требованиям поскольку `barrier` приводит к взаимоблокировке тем, что только один поток выполняет `single` раздел:

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>A.20 привязка барьера директивы

Привязка директив правила вызова для `barrier` директивы для привязки к ближайший включающий `parallel` директива. Дополнительные сведения о привязка директив, см. в разделе [разделе 2.8](2-directives.md#28-directive-binding).

В следующем примере вызов из *основной* для *sub2* является совместимым поскольку `barrier` (в *sub3*) привязывается к параллельной области в *sub2* . Вызов из *основной* для *sub1* является совместимым поскольку `barrier` привязывается к параллельной области в подпрограмме *sub2*.  Вызов из *основной* для *sub3* является совместимым поскольку `barrier` не выполняет привязку к любой параллельной области и учитывается. Кроме того `barrier` синхронизирует только команда потоков в области включающего parallel и не все потоки, созданные в *sub1*.

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>A.21 ограничение переменных области с помощью предложения private

Значения `i` и `j` в следующем примере определены при выходе из параллельной области:

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

Дополнительные сведения о `private` предложение, см. в разделе [разделе 2.7.2.1](2-directives.md#2721-private).

## <a name="a22-the-defaultnone-clause"></a>A.22 предложения default(none)

Следующий пример разделяет переменные, которые были затронуты `default(none)` предложение из переменных, которые не являются:

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

Дополнительные сведения о `default` предложение, см. в разделе [разделе 2.7.2.5](2-directives.md#2725-default).

## <a name="a23-examples-of-the-ordered-directive"></a>A.23 примеры директивы ordered

Это может быть число упорядоченных разделов с `for` указывается с помощью `ordered` предложение. Первый пример соответствует требованиям, так как API определяет следующее правило:

«Итерация цикла с `for` конструкция же не может выполняться `ordered` директив более чем один раз и он должен выполняться не более одного `ordered` директива.» (См. в разделе [разделе 2.6.6](2-directives.md#266-ordered-construct).)

В этом примере несоответствующих всех итераций выполнение двух упорядоченных разделов:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Показано в следующем примере соответствует `for` с более чем один раздел с контролем порядка:

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>A.24 примеры предложения private

[Частного](2-directives.md#2721-private) предложении параллельной области действует только лексической области региона, но не для динамического экстент области.  Таким образом, в следующем примере, любое использование переменной *a* в `for` цикла в подпрограмме *f* ссылается на частную копию *a*, а использование в подпрограмма *g* ссылается на глобальную *a*.

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>A.25 примеры предложения атрибута данных copyprivate

**Пример 1**. [Copyprivate](2-directives.md#2728-copyprivate) предложение может использоваться для передачи значений, полученных одним потоком непосредственно ко всем экземплярам частных переменных в других потоках.

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

Если процедуры *init* вызывается из последовательной региона, его поведение не влияет наличие директив. После вызова *get_values* процедура выполнена одним потоком, ни один поток покидает конструкция до закрытых объектов, обозначенный *a*, *b*, *x*, и *y* во всех потоках становятся определили со значениями, считанными.

**Пример 2**. В отличие от предыдущего примера предположим, что свойство для чтения должна быть выполнена пользователем определенного потока, предположим, что основной поток. В этом случае `copyprivate` предложение нельзя использовать непосредственно сделать вещания, но его можно использовать для предоставления доступа к общей временный объект.

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**Пример 3.** Предположим, что количество блокировок объектов, необходимых внутри параллельной области невозможно легко определить перед вводом. `copyprivate` Предложение может использоваться для предоставления доступа к объектам совмещаемую блокировку, которые назначаются в направлении, область параллельной обработки.

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>A.26 директива threadprivate

Следующие примеры демонстрируют, как использовать [threadprivate](2-directives.md#271-threadprivate-directive) директиву, чтобы каждый поток отдельный счетчик.

### <a name="example-1"></a>Пример 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>Пример 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>Массивы переменной длины C99 A.27

В следующем примере демонстрируется использование массивов переменной длины C99 (Vla) в [firstprivate](2-directives.md#2722-firstprivate) директива.

> [!NOTE]
> Массивы переменной длины не поддерживаются в Visual C++.

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-numthreads-clause"></a>A.28 предложения num_threads

В следующем примере демонстрируется [num_threads](2-directives.md#23-parallel-construct) предложение. Область параллельной обработки выполняется не более 10 потоков.

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>A.29 конструкции совместной работы, внутри конструкции critical

В следующем примере показано использование конструкции совместной работы внутри `critical` построения. В этом примере является совместимым, поскольку построения совместной работы и `critical` конструкция не привязан в одном регионе parallel.

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>A.30 повторного закрытия

В следующем примере показано повторного закрытия переменных. Закрытые переменные могут быть помечены `private` попытку через вложенные директивы. Вы не должны передавать эти переменные в области включающего parallel.

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>A.31 функции блокировки поточно ориентированными

Следующие C++ примере показано, как инициализировать массив блокировок в параллельной области с помощью [функции omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions).

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
