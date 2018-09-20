---
title: Переменные среды OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b61535fd07066c4a1ee24658fdfe81047efc90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446573"
---
# <a name="openmp-environment-variables"></a>Переменные среды OpenMP

Ссылки на переменные среды, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие переменные среды. Эти переменные среды считываются при запуске программы и изменения их значения игнорируются во время выполнения (например, с помощью [_putenv, _wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)).

|переменная среды;|Описание|
|--------------------------|-----------------|
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|Указывает, может ли изменять количество потоков в параллельной области OpenMP, время выполнения.|
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|Указывает, включен ли вложенный параллелизм, если не включена или отключена с помощью вложенных параллелизма `omp_set_nested`.|
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|Задает максимальное число потоков в параллельной области, если не переопределено [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [num_threads](../../../parallel/openmp/reference/num-threads.md).|
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|Изменяет поведение [расписание](../../../parallel/openmp/reference/schedule.md) предложение при `schedule(runtime)` указывается в `for` или `parallel for` директива.|

## <a name="see-also"></a>См. также

[Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)