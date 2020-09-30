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
ms.openlocfilehash: 3f9117c531bdf0c5a0c94e0b18a055591f431036
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503757"
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP

Предоставляет ссылки на переменные среды, используемые в API OpenMP.

Visual C++ реализация стандарта OpenMP включает следующие переменные среды. Эти переменные среды считываются при запуске программы, и изменения их значений игнорируются во время выполнения (например, с помощью [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|Переменная среды|Описание|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|Изменяет поведение предложения [Schedule](openmp-clauses.md#schedule) , если `schedule(runtime)` указано в `for` `parallel for` директиве или.|
|[OMP_NUM_THREADS](#omp-num-threads)|Задает максимальное число потоков в параллельной области, если оно не переопределено с помощью [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads](openmp-clauses.md#num-threads).|
|[OMP_DYNAMIC](#omp-dynamic)|Указывает, может ли время выполнения OpenMP настраивать количество потоков в параллельной области.|
|[OMP_NESTED](#omp-nested)|Указывает, включен ли вложенный параллелизм, если только не включен или отключен вложенный параллелизм с `omp_set_nested` .|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a> OMP_DYNAMIC

Указывает, может ли время выполнения OpenMP настраивать количество потоков в параллельной области.

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Remarks

`OMP_DYNAMIC`Переменная среды может быть переопределена функцией [omp_set_dynamic](openmp-functions.md#omp-set-dynamic) .

Значением по умолчанию в Visual C++ реализации стандарта OpenMP является `OMP_DYNAMIC=FALSE` .

Дополнительные сведения см. в статье [4,3 OMP_DYNAMIC](../4-environment-variables.md#43-omp_dynamic).

### <a name="example"></a>Пример

Следующая команда задает `OMP_DYNAMIC` для переменной среды значение true:

```cmd
set OMP_DYNAMIC=TRUE
```

Следующая команда отображает текущее значение `OMP_DYNAMIC` переменной среды:

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a> OMP_NESTED

Указывает, включен ли вложенный параллелизм, если только не включен или отключен вложенный параллелизм с `omp_set_nested` .

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Remarks

`OMP_NESTED`Переменная среды может быть переопределена функцией [omp_set_nested](openmp-functions.md#omp-set-nested) .

Значением по умолчанию в Visual C++ реализации стандарта OpenMP является `OMP_DYNAMIC=FALSE` .

Дополнительные сведения см. в статье [4,4 OMP_NESTED](../4-environment-variables.md#44-omp_nested).

### <a name="example"></a>Пример

Следующая команда задает `OMP_NESTED` для переменной среды значение true:

```cmd
set OMP_NESTED=TRUE
```

Следующая команда отображает текущее значение `OMP_NESTED` переменной среды:

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a> OMP_NUM_THREADS

Задает максимальное число потоков в параллельной области, если оно не переопределено с помощью [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads](openmp-clauses.md#num-threads).

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Параметры

*num*<br/>
Максимальное число потоков в параллельной области до 64 в реализации Visual C++.

### <a name="remarks"></a>Remarks

`OMP_NUM_THREADS`Переменная среды может быть переопределена функцией [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) или [num_threads](openmp-clauses.md#num-threads).

Значением по умолчанию `num` в Visual C++ реализации стандарта OpenMP является число виртуальных процессоров, включая процессоры Hyper-Threading.

Дополнительные сведения см. в статье [4,2 OMP_NUM_THREADS](../4-environment-variables.md#42-omp_num_threads).

### <a name="example"></a>Пример

Следующая команда задает `OMP_NUM_THREADS` для переменной среды следующее значение `16` :

```cmd
set OMP_NUM_THREADS=16
```

Следующая команда отображает текущее значение `OMP_NUM_THREADS` переменной среды:

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a> OMP_SCHEDULE

Изменяет поведение предложения [Schedule](openmp-clauses.md#schedule) , если `schedule(runtime)` указано в `for` `parallel for` директиве или.

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Параметры

*size*<br/>
Используемых Задает размер итераций. *Размер* должен быть положительным целым числом. Значение по умолчанию — `1` , за исключением случаев, когда *тип* является статическим. Недопустимо, если *тип* — `runtime` .

*type*<br/>
Тип расписаний:,, `dynamic` `guided` `runtime` или `static` .

### <a name="remarks"></a>Remarks

Значением по умолчанию в Visual C++ реализации стандарта OpenMP является `OMP_SCHEDULE=static,0` .

Дополнительные сведения см. в статье [4,1 OMP_SCHEDULE](../4-environment-variables.md#41-omp_schedule).

### <a name="example"></a>Пример

Следующая команда задает `OMP_SCHEDULE` переменную среды:

```cmd
set OMP_SCHEDULE="guided,2"
```

Следующая команда отображает текущее значение `OMP_SCHEDULE` переменной среды:

```cmd
set OMP_SCHEDULE
```
