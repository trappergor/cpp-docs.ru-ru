---
title: A.15 Определение количества используемых потоков | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1042b4871f53bddb5cff894330f3afe7d8a088ef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428745"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Определение количества используемых потоков

Рассмотрим следующий пример неверные (для [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на стр. 37):

```
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()` Вызов возвращает значение 1 в последовательной раздела кода, поэтому *np* всегда будет равно 1 в предыдущем примере. Чтобы определить количество потоков, которые будут развернуты для параллельной области, внутри параллельной области должен быть вызов.

Приведенный ниже показано, как переписывать этой программы, не включая запрос для потоков:

```
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```