---
title: Функции OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de3ea54a1526e7b340f804a21d990b6a691d0eee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066426"
---
# <a name="openmp-functions"></a>Функции OpenMP

Ссылки на функции, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие функции.

|Функция|Описание|
|--------|-----------|
|[omp_destroy_lock](#omp-destroy-lock)|Отменяет инициализацию блокировку.|
|[omp_destroy_nest_lock](#omp-destroy-nest-lock)|Отменяет инициализацию вкладываемых блокировок.|
|[omp_get_dynamic](#omp-get-dynamic)|Возвращает значение, указывающее, если число потоков, доступных в будущих параллельных регионов может регулироваться путем время выполнения.|
|[omp_get_max_threads](#omp-get-max-threads)|Возвращает целое число, равное или больше, чем количество потоков, которые будут доступны, если параллельной области без [num_threads](openmp-clauses.md#num-threads) были определены в этой точке в коде.|
|[omp_get_nested](#omp-get-nested)|Возвращает значение, указывающее, включена ли вложенные параллелизма.|
|[omp_get_num_procs](#omp-get-num-procs)|Возвращает количество процессоров, доступных при вызове функции.|
|[omp_get_num_threads](#omp-get-num-threads)|Возвращает количество потоков в параллельной области.|
|[omp_get_thread_num](#omp-get-thread-num)|Возвращает количество потоков потока, выполняющегося в его поток команды.|
|[omp_get_wtick](#omp-get-wtick)|Возвращает количество секунд между тактов процессора.|
|[omp_get_wtime](#omp-get-wtime)|Возвращает значение в секундах времени, прошедшего с какой-то момент.|
|[omp_in_parallel](#omp-in-parallel)|Возвращает ненулевое значение, при вызове из внутри параллельной области.|
|[omp_init_lock](#omp-init-lock)|Инициализирует простой блокировки.|
|[omp_init_nest_lock](#omp-init-nest-lock)|Инициализирует блокировку.|
|[omp_set_dynamic](#omp-set-dynamic)|Указывает, что количество потоков, доступных в будущих параллельных регионов может регулироваться путем время выполнения.|
|[omp_set_lock](#omp-set-lock)|Блокирует выполнение потока, пока не станет доступна блокировка.|
|[omp_set_nest_lock](#omp-set-nest-lock)|Блокирует выполнение потока, пока не станет доступна блокировка.|
|[omp_set_nested](#omp-set-nested)|Использовать вложенные параллелизм.|
|[omp_set_num_threads](#omp-set-num-threads)|Задает число потоков в будущих параллельных регионов, если не переопределено [num_threads](openmp-clauses.md#num-threads) предложение.|
|[omp_test_lock](#omp-test-lock)|Пытается установить блокировку, но не блокирует выполнение потока.|
|[omp_test_nest_lock](#omp-test-nest-lock)|Пытается задать вкладываемых блокировок, но не блокирует выполнение потока.|
|[omp_unset_lock](#omp-unset-lock)|Снимает блокировку.|
|[omp_unset_nest_lock](#omp-unset-nest-lock)|Освобождает блокировку вкладываемых.|

## <a name="omp-destroy-lock"></a>функции omp_destroy_lock

Отменяет инициализацию блокировку.

```
void omp_destroy_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](openmp-data-types.md#omp-lock-t) , инициализированный с [функции omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.2 функции omp_destroy_lock и omp_destroy_nest_lock функции](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [функции omp_init_lock](#omp-init-lock) пример использования `omp_destroy_lock`.

## <a name="omp-destroy-nest-lock"></a>omp_destroy_nest_lock

Отменяет инициализацию вкладываемых блокировок.

```
void omp_destroy_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , инициализированный с [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.2 функции omp_destroy_lock и omp_destroy_nest_lock функции](../../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [omp_init_nest_lock](#omp-init-nest-lock) пример использования `omp_destroy_nest_lock`.

## <a name="omp-get-dynamic"></a>omp_get_dynamic

Возвращает значение, указывающее, если число потоков, доступных в будущих параллельных регионов может регулироваться путем время выполнения.

```
int omp_get_dynamic();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение означает, что потоки будет скорректирована динамически.

### <a name="remarks"></a>Примечания

Динамическую настройку потоков указывается с помощью [omp_set_dynamic](#omp-set-dynamic) и [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic).

Дополнительные сведения см. в разделе [3.1.7 функция omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Пример

См. в разделе [omp_set_dynamic](#omp-set-dynamic) пример использования `omp_get_dynamic`.

## <a name="omp-get-max-threads"></a>omp_get_max_threads

Возвращает целое число, равное или больше, чем количество потоков, которые будут доступны, если параллельной области без [num_threads](openmp-clauses.md#num-threads) были определены в этой точке в коде.

```
int omp_get_max_threads( )
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.3 функция omp_get_max_threads](../../../parallel/openmp/3-1-3-omp-get-max-threads-function.md).

### <a name="example"></a>Пример

```
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

Возвращает значение, указывающее, включена ли вложенные параллелизма.

```
int omp_get_nested( );
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение означает, что включен вложенный параллелизм.

### <a name="remarks"></a>Примечания

Вложенный параллелизм указывается с помощью [omp_set_nested](#omp-set-nested) и [OMP_NESTED](openmp-environment-variables.md#omp-nested).

Дополнительные сведения см. в разделе [3.1.10 функция omp_get_nested](../../../parallel/openmp/3-1-10-omp-get-nested-function.md).

### <a name="example"></a>Пример

См. в разделе [omp_set_nested](#omp-set-nested) пример использования `omp_get_nested`.

## <a name="omp-get-num-procs"></a>omp_get_num_procs

Возвращает количество процессоров, доступных при вызове функции.

```
int omp_get_num_procs();
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.5 функция omp_get_num_procs](../../../parallel/openmp/3-1-5-omp-get-num-procs-function.md).

### <a name="example"></a>Пример

```
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

Возвращает количество потоков в параллельной области.

```
int omp_get_num_threads( );
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.2 функция omp_get_num_threads](../../../parallel/openmp/3-1-2-omp-get-num-threads-function.md).

### <a name="example"></a>Пример

```
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

Возвращает количество потоков потока, выполняющегося в его поток команды.

```
int omp_get_thread_num( );
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.4 функция omp_get_thread_num](../../../parallel/openmp/3-1-4-omp-get-thread-num-function.md).

### <a name="example"></a>Пример

См. в разделе [параллельных](openmp-directives.md#parallel) пример использования `omp_get_thread_num`.

## <a name="omp-get-wtick"></a>omp_get_wtick

Возвращает количество секунд между тактов процессора.

```
double omp_get_wtick( );
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.3.2 функция omp_get_wtick](../../../parallel/openmp/3-3-2-omp-get-wtick-function.md).

### <a name="example"></a>Пример

См. в разделе [omp_get_wtime](#omp-get-wtime) пример использования `omp_get_wtick`.

## <a name="omp-get-wtime"></a>omp_get_wtime

Возвращает значение в секундах времени, прошедшего с какой-то момент.

```
double omp_get_wtime( );
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение в секундах времени, прошедшего с некоторые произвольной, но согласованные точки.

### <a name="remarks"></a>Примечания

Во время выполнения программы, выполнения возможных будущих сравнений будет оставаться неизменным этой точки.

Дополнительные сведения см. в разделе [3.3.1 функция omp_get_wtime](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md).

### <a name="example"></a>Пример

```
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

Возвращает ненулевое значение, при вызове из внутри параллельной области.

```
int omp_in_parallel( );
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.6 функция omp_in_parallel](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

### <a name="example"></a>Пример

```
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

## <a name="omp-init-lock"></a>функции omp_init_lock

Инициализирует простой блокировки.

```
void omp_init_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](openmp-data-types.md#omp-lock-t).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.1 функции omp_init_lock и omp_init_nest_lock функции](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Пример

```
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

```
void omp_init_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t).

### <a name="remarks"></a>Примечания

Исходное количество вложенности равен нулю.

Дополнительные сведения см. в разделе [3.2.1 функции omp_init_lock и omp_init_nest_lock функции](../../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md).

### <a name="example"></a>Пример

```
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

Указывает, что количество потоков, доступных в будущих параллельных регионов может регулироваться путем время выполнения.

```
void omp_set_dynamic(
   int val
);
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Значение, указывающее, если число потоков, доступных в будущих параллельных регионов может корректироваться средой выполнения.  Если значение ненулевое, среда выполнения можно изменить число потоков, если значение равно нулю, среда выполнения не измените не динамически число потоков.

### <a name="remarks"></a>Примечания

Число потоков никогда не превысит значение, заданное параметром [omp_set_num_threads](#omp-set-num-threads) или [OMP_NUM_THREADS](openmp-environment-variables.md#omp-num-threads).

Используйте [omp_get_dynamic](#omp-get-dynamic) для отображения текущего значения параметра `omp_set_dynamic`.

Параметр для `omp_set_dynamic` переопределит параметр из [OMP_DYNAMIC](openmp-environment-variables.md#omp-dynamic) переменной среды.

Дополнительные сведения см. в разделе [3.1.7 функция omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).

### <a name="example"></a>Пример

```
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

## <a name="omp-set-lock"></a>функции omp_set_lock

Блокирует выполнение потока, пока не станет доступна блокировка.

```
void omp_set_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](openmp-data-types.md#omp-lock-t) , инициализированный с [функции omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.3 функции omp_set_lock и omp_set_nest_lock функции](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Примеры

См. в разделе [функции omp_init_lock](#omp-init-lock) пример использования `omp_set_lock`.

## <a name="omp-set-nest-lock"></a>omp_set_nest_lock

Блокирует выполнение потока, пока не станет доступна блокировка.

```
void omp_set_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , инициализированный с [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.3 функции omp_set_lock и omp_set_nest_lock функции](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).

### <a name="examples"></a>Примеры

См. в разделе [omp_init_nest_lock](#omp-init-nest-lock) пример использования `omp_set_nest_lock`.

## <a name="omp-set-nested"></a>omp_set_nested

Использовать вложенные параллелизм.

```
void omp_set_nested(
   int val
);
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Ненулевое значение Включить вложенные параллелизма, ноль отключает вложенных параллелизма.

### <a name="remarks"></a>Примечания

Вложенные OMP параллелизма можно включить с помощью `omp_set_nested`, или установив [OMP_NESTED](openmp-environment-variables.md#omp-nested) переменной среды.

Параметр для `omp_set_nested` переопределит параметр из `OMP_NESTED` переменной среды.

Включение в переменной среды может нарушить работу приложения в противном случае оперативной, поскольку число потоков растет в геометрической прогрессии при наличии вложенных параллельных регионов.  Например, функция, которая также выполняет рекурсивный просмотр шесть раз с количеством OMP потоков, равное 4 требуется 4096 (4 в степень 6) потоки. За исключением с приложениями ввода-вывода приложения обычно производительность при наличии нескольких потоков, чем процессоров.

Используйте [omp_get_nested](#omp-get-nested) для отображения текущего значения параметра `omp_set_nested`.

Дополнительные сведения см. в разделе [3.1.9 функция omp_set_nested](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).

### <a name="example"></a>Пример

```
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

Задает число потоков в будущих параллельных регионов, если не переопределено [num_threads](openmp-clauses.md#num-threads) предложение.

```
void omp_set_num_threads(
   int num_threads
);
```

### <a name="parameters"></a>Параметры

*num_threads*<br/>
Число потоков в параллельной области.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.1.1 функция omp_set_num_threads](../../../parallel/openmp/3-1-1-omp-set-num-threads-function.md).

### <a name="example"></a>Пример

См. в разделе [omp_get_num_threads](#omp-get-num-threads) пример использования `omp_set_num_threads`.

## <a name="omp-test-lock"></a>функции omp_test_lock

Пытается установить блокировку, но не блокирует выполнение потока.

```
int omp_test_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](openmp-data-types.md#omp-lock-t) , инициализированный с [функции omp_init_lock](#omp-init-lock).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.5 функции omp_test_lock и omp_test_nest_lock функции](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Пример

```
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

Пытается задать вкладываемых блокировок, но не блокирует выполнение потока.

```
int omp_test_nest_lock(
   omp_nest_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , инициализированный с [omp_init_nest_lock](#omp-init-nest-lock).

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.5 функции omp_test_lock и omp_test_nest_lock функции](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).

### <a name="example"></a>Пример

```
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

## <a name="omp-unset-lock"></a>функции omp_unset_lock

Снимает блокировку.

```
void omp_unset_lock(
   omp_lock_t *lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_lock_t](openmp-data-types.md#omp-lock-t) , инициализированный с [функции omp_init_lock](#omp-init-lock), владельцем которых является поток и выполняется в функцию.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.4 функции omp_unset_lock и omp_unset_nest_lock функции](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [функции omp_init_lock](#omp-init-lock) пример использования `omp_unset_lock`.

## <a name="omp-unset-nest-lock"></a>omp_unset_nest_lock

Освобождает блокировку вкладываемых.

```
void omp_unset_nest_lock( 
   omp_nest_lock_t *lock 
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Переменная типа [omp_nest_lock_t](openmp-data-types.md#omp-nest-lock-t) , инициализированный с [omp_init_nest_lock](#omp-init-nest-lock), владельцем которых является поток и выполняется в функцию.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [3.2.4 функции omp_unset_lock и omp_unset_nest_lock функции](../../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md).

### <a name="example"></a>Пример

См. в разделе [omp_init_nest_lock](#omp-init-nest-lock) пример использования `omp_unset_nest_lock`.
