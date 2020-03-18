---
title: Переменные среды OpenMP
ms.date: 03/20/2019
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: 838427320fcb68cedb97b36156fc18002ed962d8
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424131"
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP

Предоставляет ссылки на переменные среды, используемые в API OpenMP.

Визуальная C++ реализация стандарта OpenMP включает следующие переменные среды. Эти переменные среды считываются при запуске программы, и изменения их значений игнорируются во время выполнения (например, с помощью [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|Переменная среды|Description|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|Изменяет поведение предложения [Schedule](openmp-clauses.md#schedule) , если `schedule(runtime)` указана в директиве `for` или `parallel for`.|
|[OMP_NUM_THREADS](#omp-num-threads)|Задает максимальное число потоков в параллельной области, если оно не переопределено с помощью [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads](openmp-clauses.md#num-threads).|
|[OMP_DYNAMIC](#omp-dynamic)|Указывает, может ли время выполнения OpenMP настраивать количество потоков в параллельной области.|
|[OMP_NESTED](#omp-nested)|Указывает, включен ли вложенный параллелизм, если только не включен или отключен вложенный параллелизм с `omp_set_nested`.|

## <a name="omp-dynamic"></a>OMP_DYNAMIC

Указывает, может ли время выполнения OpenMP настраивать количество потоков в параллельной области.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Remarks

Переменная среды `OMP_DYNAMIC` может быть переопределена функцией [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) .

Значение по умолчанию в визуальной C++ реализации стандарта OpenMP — `OMP_DYNAMIC=FALSE`.

Дополнительные сведения см. в статье [4,3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).

### <a name="example"></a>Пример

Следующая команда задает для переменной среды `OMP_DYNAMIC` значение TRUE:

```cmd
set OMP_DYNAMIC=TRUE
```

Следующая команда отображает текущее значение переменной среды `OMP_DYNAMIC`:

```cmd
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

Указывает, включен ли вложенный параллелизм, если только не включен или отключен вложенный параллелизм с `omp_set_nested`.

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Remarks

Переменная среды `OMP_NESTED` может быть переопределена функцией [omp_set_nested](openmp-functions.md#omp-set-nested) .

Значение по умолчанию в визуальной C++ реализации стандарта OpenMP — `OMP_DYNAMIC=FALSE`.

Дополнительные сведения см. в статье [4,4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

### <a name="example"></a>Пример

Следующая команда задает для переменной среды `OMP_NESTED` значение TRUE:

```cmd
set OMP_NESTED=TRUE
```

Следующая команда отображает текущее значение переменной среды `OMP_NESTED`:

```cmd
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

Задает максимальное число потоков в параллельной области, если оно не переопределено с помощью [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads](openmp-clauses.md#num-threads).

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Параметры

*num*<br/>
Максимальное число потоков в параллельной области до 64 в реализации визуального C++ элемента.

### <a name="remarks"></a>Remarks

Переменная среды `OMP_NUM_THREADS` может быть переопределена функцией [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads](openmp-clauses.md#num-threads).

Значением по умолчанию для `num` в C++ реализации стандарта OpenMP является число виртуальных процессоров, включая процессоры Hyper-Threading.

Дополнительные сведения см. в статье [4,2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).

### <a name="example"></a>Пример

Следующая команда задает для переменной среды `OMP_NUM_THREADS` значение `16`:

```cmd
set OMP_NUM_THREADS=16
```

Следующая команда отображает текущее значение переменной среды `OMP_NUM_THREADS`:

```cmd
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

Изменяет поведение предложения [Schedule](openmp-clauses.md#schedule) , если `schedule(runtime)` указана в директиве `for` или `parallel for`.

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Параметры

*size*<br/>
Используемых Задает размер итераций. *Размер* должен быть положительным целым числом. Значение по умолчанию — `1`, за исключением случаев, когда *тип* является статическим. Недопустимо, если *тип* — `runtime`.

*type*<br/>
Тип расписания: `dynamic`, `guided`, `runtime`или `static`.

### <a name="remarks"></a>Remarks

Значение по умолчанию в визуальной C++ реализации стандарта OpenMP — `OMP_SCHEDULE=static,0`.

Дополнительные сведения см. в статье [4,1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).

### <a name="example"></a>Пример

Следующая команда задает переменную среды `OMP_SCHEDULE`:

```cmd
set OMP_SCHEDULE="guided,2"
```

Следующая команда отображает текущее значение переменной среды `OMP_SCHEDULE`:

```cmd
set OMP_SCHEDULE
```
