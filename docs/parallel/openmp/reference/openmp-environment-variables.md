---
title: Переменные среды OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 10/23/2018
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
dev_langs:
- C++
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 395494431c3942832a64cf64c9c150f643389062
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990234"
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP

Ссылки на переменные среды, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие переменные среды. Эти переменные среды считываются при запуске программы и изменения их значения игнорируются во время выполнения (например, с помощью [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

переменная среды;                | Описание
----------------------------------- | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[OMP_DYNAMIC](#omp-dynamic)         | Указывает, может ли изменять количество потоков в параллельной области OpenMP, время выполнения.
[OMP_NESTED](#omp-nested)           | Указывает, включен ли вложенный параллелизм, если не включена или отключена с помощью вложенных параллелизма `omp_set_nested`.
[OMP_NUM_THREADS](#omp-num-threads) | Задает максимальное число потоков в параллельной области, если не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](openmp-clauses.md#num-threads).
[OMP_SCHEDULE](#omp-schedule)       | Изменяет поведение [расписание](openmp-clauses.md#schedule) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директива.

## <a name="omp-dynamic"></a>OMP_DYNAMIC

Указывает, может ли изменять количество потоков в параллельной области OpenMP, время выполнения.

```
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>Примечания

`OMP_DYNAMIC` Переменной среды могут быть переопределены [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) функции.

Значение по умолчанию в Visual C++ реализации стандарта OpenMP — `OMP_DYNAMIC=FALSE`.

Дополнительные сведения см. в разделе [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).

### <a name="example"></a>Пример

Следующая команда задает `OMP_DYNAMIC` переменной среды в значение TRUE:

```
set OMP_DYNAMIC=TRUE
```

Следующая команда отображает текущее значение параметра `OMP_DYNAMIC` переменной среды:

```
set OMP_DYNAMIC
```

## <a name="omp-nested"></a>OMP_NESTED

Указывает, включен ли вложенный параллелизм, если не включена или отключена с помощью вложенных параллелизма `omp_set_nested`.

```
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>Примечания

`OMP_NESTED` Переменной среды могут быть переопределены [omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md) функции.

Значение по умолчанию в Visual C++ реализации стандарта OpenMP — `OMP_DYNAMIC=FALSE`.

Дополнительные сведения см. в разделе [4.4 OMP_NESTED](../../../parallel/openmp/4-4-omp-nested.md).

### <a name="example"></a>Пример

Следующая команда задает `OMP_NESTED` переменной среды в значение TRUE:

```
set OMP_NESTED=TRUE
```

Следующая команда отображает текущее значение параметра `OMP_NESTED` переменной среды:

```
set OMP_NESTED
```

## <a name="omp-num-threads"></a>OMP_NUM_THREADS

Задает максимальное число потоков в параллельной области, если не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](openmp-clauses.md#num-threads).

```
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>Параметры

*num*<br/>
Максимальное количество потоков в параллельной области, не более 64-разрядная реализация Visual C++.

### <a name="remarks"></a>Примечания

`OMP_NUM_THREADS` Переменной среды могут быть переопределены [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функции или [num_threads](openmp-clauses.md#num-threads).

Значение по умолчанию `num` в Visual C++ реализация стандарта OpenMP — это количество виртуальных процессоров, включая процессоры с технологией Hyper-Threading.

Дополнительные сведения см. в разделе [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md).

### <a name="example"></a>Пример

Следующая команда задает `OMP_NUM_THREADS` переменной среды до 16:

```
set OMP_NUM_THREADS=16
```

Следующая команда отображает текущее значение параметра `OMP_NUM_THREADS` переменной среды:

```
set OMP_NUM_THREADS
```

## <a name="omp-schedule"></a>OMP_SCHEDULE

Изменяет поведение [расписание](openmp-clauses.md#schedule) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директива.

```
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>Параметры

*size*<br/>
(Необязательно) Указывает размер итераций. `size` Должно быть положительным целым числом. Значение по умолчанию равно 1, за исключением случаев `type` является статическим. Не является допустимым, если `type` является `runtime`.

*type*<br/>
Тип расписания:

- `dynamic`
- `guided`
- `runtime`
- `static`

### <a name="remarks"></a>Примечания

Значение по умолчанию в Visual C++ реализации стандарта OpenMP — `OMP_SCHEDULE=static,0`.

Дополнительные сведения см. в разделе [4.1 OMP_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).

### <a name="example"></a>Пример

Следующая команда задает `OMP_SCHEDULE` переменной среды:

```
set OMP_SCHEDULE="guided,2"
```

Следующая команда отображает текущее значение параметра `OMP_SCHEDULE` переменной среды:

```
set OMP_SCHEDULE
```
