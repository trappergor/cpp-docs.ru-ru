---
title: Е. Новые функции и разъяснения в версии 2.0
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 2e186bbc82f4f43e831dd05cdded2a9e946d1dd2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362718"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>Е. Новые функции и разъяснения в версии 2.0

В этом приложении приведены ключевые изменения, внесенные в спецификации OpenMP C/C++ при переходе с версии 1.0 до версии 2.0. Ниже перечислены новые возможности, которые добавлены в спецификации:

- В OpenMP допускаются запятые [директивы](2-directives.md#21-directive-format).

- Добавление `num_threads` предложение. Это предложение позволяет пользователю запросить определенное количество потоков для [параллельной конструкции](2-directives.md#23-parallel-construct).

- [Threadprivate](2-directives.md#271-threadprivate-directive) директива была расширена для приема переменные статические области видимости блока.

- Массивы переменной длины C99 являются полными типами и могут быть указаны в любом полными типами, разрешенных, например списки `private`, `firstprivate`, и `lastprivate` предложений (см. в разделе [разделе 2.7.2](2-directives.md#272-data-sharing-attribute-clauses)).

- Можно пометить частную переменную в параллельной области [частного](2-directives.md#2721-private) попытку через вложенные директивы.

- `copyprivate` Было добавлено предложение. Он предоставляет механизм использовать частную переменную для рассылки значение из одного членом команды с другими элементами. Это альтернатива использованию общей переменной для значения, когда предоставляя общей переменной будет трудно (например, в рекурсии, требуя отдельную переменную на каждом уровне). [Copyprivate](2-directives.md#2728-copyprivate) предложение может находиться только в `single` директива.

- Добавление процедуры расписания [omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) и [omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) аналогичную подпрограммы MPI. Эти функции необходимы для wall временных интервалов времени.

- Приложение со списком [поведения, определяемые реализацией](e-implementation-defined-behaviors-in-openmp-c-cpp.md) была добавлена в OpenMP C/C++. Реализация является обязательным для определения и документировать ее поведение в таких случаях.

- Для уточнения или исправления функции в предыдущем спецификации OpenMP API C/C++ служат следующие изменения:

  - Уточнено, что поведение [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) и [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) при `omp_in_parallel` возвращает ненулевое значение не определено.

  - Уточнено [директива nesting](2-directives.md#29-directive-nesting) при использовании вложенных параллельных.

  - [Блокировки инициализации](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions) и [заблокировать уничтожения](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) функции могут быть вызваны в параллельной области.

  - Были добавлены новые примеры [приложение А](a-examples.md).