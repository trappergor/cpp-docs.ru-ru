---
title: Функции OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5daa7737f63df437f31f349a85811befe0c8f5b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425604"
---
# <a name="openmp-functions"></a>Функции OpenMP

Ссылки на функции, используемые в OpenMP API.

Реализация Visual C++ OpenMP standard включает следующие функции.

|Функция|Описание|
|--------------|-----------------|
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|Отменяет инициализацию блокировку.|
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|Отменяет инициализацию вкладываемых блокировок.|
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|Возвращает значение, указывающее, если число потоков, доступных в последующих параллельной области могут быть изменены при время выполнения.|
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|Возвращает целое число, равное или больше, чем количество потоков, которые будут доступны, если параллельной области без [num_threads](../../../parallel/openmp/reference/num-threads.md) были определены в этой точке в коде.|
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|Возвращает значение, указывающее, включена ли вложенные параллелизма.|
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|Возвращает количество процессоров, доступных при вызове функции.|
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|Возвращает количество потоков в параллельной области.|
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|Возвращает количество потоков потока, выполняющегося в его поток команды.|
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|Возвращает количество секунд между тактов процессора.|
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|Возвращает значение в секундах времени, прошедшего с какой-то момент.|
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|Возвращает ненулевое значение, при вызове из внутри параллельной области.|
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|Инициализирует простой блокировки.|
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|Инициализирует блокировку.|
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|Указывает, что количество потоков, доступных в последующих параллельной области могут быть изменены при время выполнения.|
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|Блокирует выполнение потока, пока не станет доступна блокировка.|
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|Блокирует выполнение потока, пока не станет доступна блокировка.|
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|Использовать вложенные параллелизм.|
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|Задает число потоков в последующих параллельных регионов, если не переопределено [num_threads](../../../parallel/openmp/reference/num-threads.md) предложение.|
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|Пытается установить блокировку, но не блокирует выполнение потока.|
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|Пытается задать вкладываемых блокировок, но не блокирует выполнение потока.|
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|Снимает блокировку.|
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|Освобождает блокировку вкладываемых.|

## <a name="see-also"></a>См. также

[Справочник по библиотеке](../../../parallel/openmp/reference/openmp-library-reference.md)