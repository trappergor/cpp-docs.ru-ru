---
title: "Е. Новые возможности и пояснениями, описанными в версии 2.0 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b9a661f183816fec0f7a71c990f1508338100f4d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>Е. Новые возможности и пояснениями, описанными в версии 2.0
В этом приложении перечислены ключевые изменения, внесенные в спецификации OpenMP C/C++ при переходе с версии 1.0 до версии 2.0. Ниже перечислены новые возможности, добавленные в спецификации:  
  
-   Запятые, разрешены в директивы OpenMP ([2.1 разделе](../../parallel/openmp/2-1-directive-format.md) на стр. 7).  
  
-   Добавление `num_threads` предложения. Это предложение позволяет пользователю запрашивать определенное число потоков для параллельной конструкции ([разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8).  
  
-   `threadprivate` Директива был расширен, чтобы принимать переменные статического области видимости блока ([разделе 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) на странице 23).  
  
-   Для массивов переменной длины C99 являются полными типами и таким образом может быть указан в любом полными типами разрешены, например в списках `private`, `firstprivate`, и `lastprivate` предложений ([раздел 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) на странице 25).  
  
-   Частной переменной в параллельной области личным еще раз в директиве вложенных ([раздел 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) на странице 25).  
  
-   `copyprivate` Было добавлено предложение. Он предоставляет механизм для использования частную переменную для передачи значения из одного из участников команды для других участников. Он является альтернативой использованию общей переменной для значения, когда предоставление общей переменной было бы трудно (например, в рекурсии, требует отдельной переменной на каждом уровне). `copyprivate` Предложение может находиться только в **один** директивы ([раздел 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) на странице 32).  
  
-   Добавление процедуры расписания `omp_get_wtick` и `omp_get_wtime` аналогично подпрограммы MPI. Функции, необходимые для выполнения настройку wall тактовой частоты ([раздел 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) на странице 44 и [разделе 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) на стр.).  
  
-   Добавлено приложение со списком поведений, определяемого реализацией в OpenMP C и C++. Определить и задокументировать его поведение в таких случаях требуется реализация ([приложение E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) на стр.).  
  
-   Для уточнения или исправления компонентов в предыдущей спецификации OpenMP API C/c++ выполняют следующие изменения:  
  
    -   Уточнено, что поведение `omp_set_nested` и `omp_set_dynamic` при `omp_in_parallel` возвращает ненулевое значение не определено ([раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39, и [раздел 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) на странице 40).  
  
    -   Добавлено пояснение директива nesting при использовании вложенных параллельного ([разделе 2.9](../../parallel/openmp/2-9-directive-nesting.md) на странице 33).  
  
    -   Можно вызывать функции блокировки инициализации и блокировка удаления в параллельной области ([раздел 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) на странице 42 и [раздел 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) на странице 42).  
  
    -   Были добавлены новые примеры ([приложение A](../../parallel/openmp/a-examples.md) на стр).