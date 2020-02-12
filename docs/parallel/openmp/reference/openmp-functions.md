---
title: Функции OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP functions
- omp_destroy_lock
- omp_destroy_nest_lock
- omp_get_dynamic
- omp_get_max_threads
- omp_get_nested
- omp_get_num_procs
- omp_get_num_threads
- omp_get_thread_num
- omp_get_wtick
- omp_get_wtime
- omp_in_parallel
- omp_init_lock
- omp_init_nest_lock
- omp_set_dynamic
- omp_set_lock
- omp_set_nest_lock
- omp_set_nested
- omp_set_num_threads
- omp_test_lock
- omp_test_nest_lock
- omp_unset_lock
- omp_unset_nest_lock
helpviewer_keywords:
- OpenMP functions
- omp_destroy_lock OpenMP function
- omp_destroy_nest_lock OpenMP function
- omp_get_dynamic OpenMP function
- omp_get_max_threads OpenMP function
- omp_get_nested OpenMP function
- omp_get_num_procs OpenMP function
- omp_get_num_threads OpenMP function
- omp_get_thread_num OpenMP function
- omp_get_wtick OpenMP function
- omp_get_wtime OpenMP function
- omp_in_parallel OpenMP function
- omp_init_lock OpenMP function
- omp_init_nest_lock OpenMP function
- omp_set_dynamic OpenMP function
- omp_set_lock OpenMP function
- omp_set_nest_lock OpenMP function
- omp_set_nested OpenMP function
- omp_set_num_threads OpenMP function
- omp_test_lock OpenMP function
- omp_test_nest_lock OpenMP function
- omp_unset_lock OpenMP function
- omp_unset_nest_lock OpenMP function
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
ms.openlocfilehash: 4508c683ff5d4bece290b7fef2bbd83ae8023eac
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141697"
---
# <a name="openmp-functions"></a>Функции OpenMP

Предоставляет ссылки на функции, используемые в API OpenMP.

Визуальная C++ реализация стандарта OpenMP включает следующие функции и типы данных.

Для выполнения среды:

|Компонент|Description|
|--------|-----------|
|[omp_set_num_threads](#omp-set-num-threads)|Задает число потоков в предстоящих параллельных областях, если оно не переопределено предложением [num_threads](openmp-clauses.md#num-threads) .|
|[omp_get_num_threads](#omp-get-num-threads)|Возвращает число потоков в параллельной области.|
|[omp_get_max_threads](#omp-get-max-threads)|Возвращает целое число, которое больше или равно числу потоков, которые были бы доступны, если в этой точке кода не были определены параллельные области без [num_threads](openmp-clauses.md#num-threads) .|
|[omp_get_thread_num](#omp-get-thread-num)|Возвращает номер потока потока, который исполняется в команде потока.|
|[omp_get_num_procs](#omp-get-num-procs)|Возвращает количество процессоров, доступных при вызове функции.|
|[omp_in_parallel](#omp-in-parallel)|Возвращает ненулевое значение при вызове из в параллельной области.|
|[omp_set_dynamic](#omp-set-dynamic)|Указывает, что количество потоков, доступных в предстоящих параллельных регионах, может быть скорректировано во время выполнения.|
|[omp_get_dynamic](#omp-get-dynamic)|Возвращает значение, указывающее, может ли количество потоков, доступных в будущих параллельных регионах, корректироваться во время выполнения.|
|[omp_set_nested](#omp-set-nested)|Включает вложенный параллелизм.|
|[omp_get_nested](#omp-get-nested)|Возвращает значение, указывающее, включен ли вложенный параллелизм.|

Для блокировки:

|Компонент|Description|
|--------|-----------|
|[omp_init_lock](#omp-init-lock)|Инициализирует простую блокировку.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Инициализирует блокировку.|
|[omp_destroy_lock](#omp-destroy-lock)|Отменяет инициализацию блокировки.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Отменяет инициализацию вложенной блокировки.|
|[omp_set_lock](#omp-set-lock)|Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.|
|[omp_unset_lock](#omp-unset-lock)|Снимает блокировку.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|Освобождает вложенную блокировку.|
|[omp_test_lock](#omp-test-lock)|Пытается установить блокировку, но не блокирует выполнение потока.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Пытается установить вложенную блокировку, но не блокирует выполнение потока.|

|Тип данных|Description|
|---------|-----------|
|`omp_lock_t`|Тип, который содержит состояние блокировки, доступность блокировки или принадлежность потока к блокировке.|
|`omp_nest_lock_t`|Тип, содержащий один из следующих фрагментов сведений о блокировке: доступность блокировки и идентификатор потока, владеющего блокировкой и число вложений.|

Для подпрограмм времени:

|Компонент|Description|
|--------|-----------|
|[omp_get_wtime](#omp-get-wtime)|Возвращает значение в секундах, прошедшее с момента, прошедшего с некоторой точки.|
|[omp_get_wtick](#omp-get-wtick)|Возвращает число секунд между тактовыми тактами процессора.|

## <a name="omp-destroy-lock"></a>omp_destroy_lock

Отменяет инициализацию блокировки.

```cpp
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_lock_t`, которая была инициализирована [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.2 omp_destroy_lock and omp_destroy_nest_lock functions](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Пример

Пример использования `omp_destroy_lock`см. в [omp_init_lock](#omp-init-lock) .

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Отменяет инициализацию вложенной блокировки.

```cpp
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_nest_lock_t`, которая была инициализирована [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.2 omp_destroy_lock and omp_destroy_nest_lock functions](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Пример

Пример использования `omp_destroy_nest_lock`см. в [omp_init_nest_lock](#omp-init-nest-lock) .

## <a name="omp-get-dynamic"></a>omp_get_dynamic

Возвращает значение, указывающее, может ли количество потоков, доступных в будущих параллельных регионах, корректироваться во время выполнения.

```cpp
int omp_get_dynamic();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение означает, что потоки будут динамически корректироваться.

### <a name="remarks"></a>Remarks

Динамическая настройка потоков указывается с помощью [omp_set_dynamic](#omp-set-dynamic) и [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic).

Дополнительные сведения см. в разделе [3.1.7 omp_set_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Пример

Пример использования `omp_get_dynamic`см. в [omp_set_dynamic](#omp-set-dynamic) .

## <a name="omp-get-max-threads"></a>omp_get_max_threads

Возвращает целое число, которое больше или равно числу потоков, которые были бы доступны, если в этой точке кода не были определены параллельные области без [num_threads](openmp-clauses.md#num-threads) .

```cpp
int omp_get_max_threads( )
```

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.1.3 Omp_get_max_threads Function](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md).

### <a name="example"></a>Пример

```cpp
// omp_get_max_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(8);
    printf_s("%d\n", omp_get_max_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_max_threads( ));
        }

    printf_s("%d\n", omp_get_max_threads( ));
}
```

```Output
8
8
8
8
8
```

## <a name="omp-get-nested"></a>omp_get_nested

Возвращает значение, указывающее, включен ли вложенный параллелизм.

```cpp
int omp_get_nested( );
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение означает, что вложенный параллелизм включен.

### <a name="remarks"></a>Remarks

Вложенный параллелизм указывается с помощью [omp_set_nested](#omp-set-nested) и [OMP_NESTED](openmp-environment-variables.md#omp-nested).

Дополнительные сведения см. в разделе [3.1.10 omp_get_nested Function](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

### <a name="example"></a>Пример

Пример использования `omp_get_nested`см. в [omp_set_nested](#omp-set-nested) .

## <a name="omp-get-num-procs"></a>omp_get_num_procs

Возвращает количество процессоров, доступных при вызове функции.

```cpp
int omp_get_num_procs();
```

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.1.5. omp_get_num_procs Function](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).

### <a name="example"></a>Пример

```cpp
// omp_get_num_procs.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    printf_s("%d\n", omp_get_num_procs( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_procs( ));
        }
}
```

```Output
// Expect the following output when the example is run on a two-processor machine:
2
2
```

## <a name="omp-get-num-threads"></a>omp_get_num_threads

Возвращает число потоков в параллельной области.

```cpp
int omp_get_num_threads( );
```

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.1.2 omp_get_num_threads Function](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md).

### <a name="example"></a>Пример

```cpp
// omp_get_num_threads.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_num_threads( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));

    #pragma omp parallel num_threads(3)
        #pragma omp master
        {
            printf_s("%d\n", omp_get_num_threads( ));
        }

    printf_s("%d\n", omp_get_num_threads( ));
}
```

```Output
1
4
1
3
1
```

## <a name="omp-get-thread-num"></a>omp_get_thread_num

Возвращает номер потока потока, который исполняется в команде потока.

```cpp
int omp_get_thread_num( );
```

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.1.4 omp_get_thread_num Function](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md).

### <a name="example"></a>Пример

Пример использования `omp_get_thread_num`см. в разделе [Parallel](openmp-directives.md#parallel) .

## <a name="omp-get-wtick"></a>omp_get_wtick

Возвращает число секунд между тактовыми тактами процессора.

```cpp
double omp_get_wtick( );
```

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.3.2 omp_get_wtick Function](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md).

### <a name="example"></a>Пример

Пример использования `omp_get_wtick`см. в [omp_get_wtime](#omp-get-wtime) .

## <a name="omp-get-wtime"></a>omp_get_wtime

Возвращает значение в секундах, прошедшее с момента, прошедшего с некоторой точки.

```cpp
double omp_get_wtime( );
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение в секундах, прошедшее из произвольного, но устойчивого точки.

### <a name="remarks"></a>Remarks

Эта точка будет оставаться согласованной во время выполнения программы, что делает возможными сравнения.

Дополнительные сведения см. в разделе [3.3.1 omp_get_wtime Function](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).

### <a name="example"></a>Пример

```cpp
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="omp-in-parallel"></a>omp_in_parallel

Возвращает ненулевое значение при вызове из в параллельной области.

```cpp
int omp_in_parallel( );
```

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.1.6 omp_in_parallel Function](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

### <a name="example"></a>Пример

```cpp
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="omp-init-lock"></a>omp_init_lock

Инициализирует простую блокировку.

```cpp
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_lock_t`.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.1 omp_init_lock and omp_init_nest_lock functions](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Пример

```cpp
// omp_init_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t my_lock;

int main() {
   omp_init_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num( );
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_lock(&my_lock);
         printf_s("Thread %d - starting locked region\n", tid);
         printf_s("Thread %d - ending locked region\n", tid);
         omp_unset_lock(&my_lock);
      }
   }

   omp_destroy_lock(&my_lock);
}
```

```Output
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 0 - starting locked region
Thread 0 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 1 - starting locked region
Thread 1 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 2 - starting locked region
Thread 2 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
Thread 3 - starting locked region
Thread 3 - ending locked region
```

## <a name="omp-init-nest-lock"></a>omp_init_nest_lock

Инициализирует блокировку.

```cpp
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_nest_lock_t`.

### <a name="remarks"></a>Remarks

Начальное число вложений равно нулю.

Дополнительные сведения см. в разделе [3.2.1 omp_init_lock and omp_init_nest_lock functions](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Пример

```cpp
// omp_init_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t my_lock;

void Test() {
   int tid = omp_get_thread_num( );
   omp_set_nest_lock(&my_lock);
   printf_s("Thread %d - starting nested locked region\n", tid);
   printf_s("Thread %d - ending nested locked region\n", tid);
   omp_unset_nest_lock(&my_lock);
}

int main() {
   omp_init_nest_lock(&my_lock);

   #pragma omp parallel num_threads(4)
   {
      int i, j;

      for (i = 0; i < 5; ++i) {
         omp_set_nest_lock(&my_lock);
            if (i % 3)
               Test();
            omp_unset_nest_lock(&my_lock);
        }
    }

    omp_destroy_nest_lock(&my_lock);
}
```

```Output
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 3 - starting nested locked region
Thread 3 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 2 - starting nested locked region
Thread 2 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 1 - starting nested locked region
Thread 1 - ending nested locked region
Thread 0 - starting nested locked region
Thread 0 - ending nested locked region
```

## <a name="omp-set-dynamic"></a>omp_set_dynamic

Указывает, что количество потоков, доступных в предстоящих параллельных регионах, может быть скорректировано во время выполнения.

```cpp
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Значение, указывающее, может ли количество потоков, доступных в будущих параллельных регионах, корректироваться средой выполнения. Если не равен нулю, среда выполнения может настроить количество потоков, если оно равно нулю, среда выполнения не будет динамически изменять количество потоков.

### <a name="remarks"></a>Remarks

Число потоков никогда не будет превышать значение, заданное [omp_set_num_threads](#omp-set-num-threads) или [OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads).

Чтобы отобразить текущее значение `omp_set_dynamic`, используйте [omp_get_dynamic](#omp-get-dynamic) .

Параметр `omp_set_dynamic` переопределяет значение переменной среды [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic) .

Дополнительные сведения см. в разделе [3.1.7 omp_set_dynamic Function](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Пример

```cpp
// omp_set_dynamic.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main()
{
    omp_set_dynamic(9);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_dynamic( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_dynamic( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-lock"></a>omp_set_lock

Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.

```cpp
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_lock_t`, которая была инициализирована [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.3 omp_set_lock and omp_set_nest_lock functions](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Примеры

Пример использования `omp_set_lock`см. в [omp_init_lock](#omp-init-lock) .

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

Блокирует выполнение потока до тех пор, пока блокировка не будет доступна.

```cpp
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_nest_lock_t`, которая была инициализирована [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.3 omp_set_lock and omp_set_nest_lock functions](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Примеры

Пример использования `omp_set_nest_lock`см. в [omp_init_nest_lock](#omp-init-nest-lock) .

## <a name="omp-set-nested"></a>omp_set_nested

Включает вложенный параллелизм.

```cpp
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Ненулевое значение включает вложенный параллелизм, а ноль отключает вложенный параллелизм.

### <a name="remarks"></a>Remarks

OMP Nested parallelism можно включить с помощью `omp_set_nested`или путем установки переменной среды [OMP_NESTED](openmp-environment-variables.md#omp-nested) .

Параметр `omp_set_nested` переопределяет значение переменной среды `OMP_NESTED`.

Включение переменной среды может нарушить работу другой операционной программы, так как число потоков растет экспоненциально при вложении параллельных регионов. Например, функция, которая выполняет рекурсивное шесть раз с числом запросов OMP, равным 4, требует 4 096 (4 в степени 6) потоков. За исключением приложений, связанных с вводом-выводом, производительность приложения обычно снижается, если количество потоков превышает число процессоров.

Чтобы отобразить текущее значение `omp_set_nested`, используйте [omp_get_nested](#omp-get-nested) .

Дополнительные сведения см. в разделе [3.1.9 omp_set_nested Function](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).

### <a name="example"></a>Пример

```cpp
// omp_set_nested.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_nested(1);
    omp_set_num_threads(4);
    printf_s("%d\n", omp_get_nested( ));
    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_get_nested( ));
        }
}
```

```Output
1
1
```

## <a name="omp-set-num-threads"></a>omp_set_num_threads

Задает число потоков в предстоящих параллельных областях, если оно не переопределено предложением [num_threads](openmp-clauses.md#num-threads) .

```cpp
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Параметры

*num_threads*<br/>
Число потоков в параллельной области.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.1.1 omp_set_num_threads Function](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

### <a name="example"></a>Пример

Пример использования `omp_set_num_threads`см. в [omp_get_num_threads](#omp-get-num-threads) .

## <a name="omp-test-lock"></a>omp_test_lock

Пытается установить блокировку, но не блокирует выполнение потока.

```cpp
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_lock_t`, которая была инициализирована [omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.5 omp_test_lock and omp_test_nest_lock functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Пример

```cpp
// omp_test_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_lock_t simple_lock;

int main() {
    omp_init_lock(&simple_lock);

    #pragma omp parallel num_threads(4)
    {
        int tid = omp_get_thread_num();

        while (!omp_test_lock(&simple_lock))
            printf_s("Thread %d - failed to acquire simple_lock\n",
                     tid);

        printf_s("Thread %d - acquired simple_lock\n", tid);

        printf_s("Thread %d - released simple_lock\n", tid);
        omp_unset_lock(&simple_lock);
    }

    omp_destroy_lock(&simple_lock);
}
```

```Output
Thread 1 - acquired simple_lock
Thread 1 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - acquired simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 2 - released simple_lock
Thread 0 - failed to acquire simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - acquired simple_lock
Thread 3 - failed to acquire simple_lock
Thread 0 - released simple_lock
Thread 3 - failed to acquire simple_lock
Thread 3 - acquired simple_lock
Thread 3 - released simple_lock
```

## <a name="omp-test-nest-lock"></a>omp_test_nest_lock

Пытается установить вложенную блокировку, но не блокирует выполнение потока.

```cpp
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_nest_lock_t`, которая была инициализирована [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.5 omp_test_lock and omp_test_nest_lock functions](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Пример

```cpp
// omp_test_nest_lock.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

omp_nest_lock_t nestable_lock;

int main() {
   omp_init_nest_lock(&nestable_lock);

   #pragma omp parallel num_threads(4)
   {
      int tid = omp_get_thread_num();
      while (!omp_test_nest_lock(&nestable_lock))
         printf_s("Thread %d - failed to acquire nestable_lock\n",
                tid);

      printf_s("Thread %d - acquired nestable_lock\n", tid);

      if (omp_test_nest_lock(&nestable_lock)) {
         printf_s("Thread %d - acquired nestable_lock again\n",
                tid);
         printf_s("Thread %d - released nestable_lock\n",
                tid);
         omp_unset_nest_lock(&nestable_lock);
      }

      printf_s("Thread %d - released nestable_lock\n", tid);
      omp_unset_nest_lock(&nestable_lock);
   }

   omp_destroy_nest_lock(&nestable_lock);
}
```

```Output
Thread 1 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 1 - released nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock
Thread 0 - failed to acquire nestable_lock
Thread 3 - acquired nestable_lock again
Thread 0 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 3 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - acquired nestable_lock again
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 0 - released nestable_lock
Thread 2 - failed to acquire nestable_lock
Thread 2 - acquired nestable_lock
Thread 2 - acquired nestable_lock again
Thread 2 - released nestable_lock
Thread 2 - released nestable_lock
```

## <a name="omp-unset-lock"></a>omp_unset_lock

Снимает блокировку.

```cpp
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_lock_t`, которая была инициализирована [omp_init_lock](#omp-init-lock), принадлежит потоку и выполняется в функции.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.4 omp_unset_lock and omp_unset_nest_lock functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Пример

Пример использования `omp_unset_lock`см. в [omp_init_lock](#omp-init-lock) .

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

Освобождает вложенную блокировку.

```cpp
void omp_unset_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа `omp_nest_lock_t`, которая была инициализирована [omp_init_nest_lock](#omp-init-nest-lock), принадлежит потоку и выполняется в функции.

### <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [3.2.4 omp_unset_lock and omp_unset_nest_lock functions](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Пример

Пример использования `omp_unset_nest_lock`см. в [omp_init_nest_lock](#omp-init-nest-lock) .
