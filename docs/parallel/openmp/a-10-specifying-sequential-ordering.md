---
title: A.10   Задание последовательного упорядочивания
ms.date: 11/04/2016
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
ms.openlocfilehash: 4e3a146e1bca988f46cf7a7ee504644f96dab67e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575257"
---
# <a name="a10---specifying-sequential-ordering"></a>A.10   Задание последовательного упорядочивания

Упорядоченные разделы ([разделе 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) на стр. 22) полезны для последовательное упорядочение в результате работа, выполняемая в параллельном режиме. Следующая программа выводит индексы в последовательном порядке:

```
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```