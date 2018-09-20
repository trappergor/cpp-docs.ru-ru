---
title: A.20 привязка директив barrier | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 628920caa6a122230f42394cc757e3abdb1874cd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381313"
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