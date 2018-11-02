---
title: A.20   Привязка директив barrier
ms.date: 11/04/2016
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
ms.openlocfilehash: cf6f20a8539c47ca529af93e65f3a5fe244228d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652950"
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   Привязка директив barrier

Привязка директив правила вызова для **барьера** директивы для привязки к ближайший включающий `parallel` директива. Дополнительные сведения о привязка директив, см. в разделе [2.8 разделе](../../parallel/openmp/2-8-directive-binding.md) на стр.

В следующем примере вызов из *основной* для *sub2* является совместимым поскольку **барьера** (в *sub3*) привязывается к параллельной области в *sub2*. Вызов из *основной* для *sub1* является совместимым поскольку **барьера** привязывается к параллельной области в подпрограмме *sub2*.  Вызов из *основной* для *sub3* является совместимым поскольку **барьера** не обеспечивает и привязку к любой параллельной области и учитывается. Также Обратите внимание, что **барьера** синхронизирует только команда потоков в области включающего parallel и не все потоки, созданные в *sub1*.

```
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```