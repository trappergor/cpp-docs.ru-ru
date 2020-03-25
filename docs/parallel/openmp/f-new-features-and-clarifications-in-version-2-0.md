---
title: Е. Новые функции и разъяснения в версии 2.0
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 8cd82000992ab957bf2c41f11deccd65e2e6ea8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215037"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>Е. Новые функции и разъяснения в версии 2.0

В этом приложении приведены основные изменения, внесенные в спецификацию OpenMPC++ C/в переходе с версии 1,0 на версию 2,0. Следующие элементы — это новые функции, добавленные в спецификацию.

- В [директивах](2-directives.md#21-directive-format)OpenMP допускаются запятые.

- Добавление предложения `num_threads`. Это предложение позволяет пользователю запрашивать определенное количество потоков для [параллельной конструкции](2-directives.md#23-parallel-construct).

- Директива [threadprivate](2-directives.md#271-threadprivate-directive) была расширена для приема статических переменных области видимости блока.

- C99 массивы переменной длины являются полными типами и могут быть указаны в любом месте, допускаются все типы, например в списках `private`, `firstprivate`и `lastprivate` (см. [раздел 2.7.2](2-directives.md#272-data-sharing-attribute-clauses)).

- Закрытая переменная в параллельной области может быть помечена как [Частная](2-directives.md#2721-private) в вложенной директиве.

- Добавлено предложение `copyprivate`. Он предоставляет механизм использования закрытой переменной для передачи значения из одного члена команды в другие члены группы. Это альтернатива использованию общей переменной для значения при предоставлении такой общей переменной сложной (например, в рекурсии, для которой требуется другая переменная на каждом уровне). Предложение [copyprivate](2-directives.md#2728-copyprivate) может использоваться только в директиве `single`.

- Добавление подпрограмм времени [omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) и [omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) аналогично подалгоритмам MPI. Эти функции необходимы для работы со временем почасовой работы стены.

- Добавлено приложение со списком [поведений, определяемых реализацией](e-implementation-defined-behaviors-in-openmp-c-cpp.md) , в OpenMPC++ C/. Реализация необходима для определения и документирования его поведения в таких случаях.

- Следующие изменения служат для уточнения или исправления функций в предыдущей спецификации API OpenMP для C/C++:

  - Разъяснено, что поведение [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) и [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) , когда `omp_in_parallel` возвращает ненулевое значение, не определено.

  - Уточнена [вложенность директив](2-directives.md#29-directive-nesting) , если используется вложенная параллельная инструкция.

  - Функции [уничтожения](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions) и [инициализации блокировки](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions) можно вызывать в параллельной области.

  - В [приложение а](a-examples.md)добавлены новые примеры.
