---
title: Пример A.24 закрытый предложения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f8d07f2d95b565077f5dfd78fdc4ff6edf30216
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="a24---example-of-the-private-clause"></a>A.24   Примеры предложения private
`private` Предложение ([раздел 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) на странице 25) параллельной области действует только лексическая область области, а не динамические экстент области.  Таким образом, в следующем примере, любое использование переменной *a* в `for` цикла в подпрограмме *f* ссылается на частную копию *a*, а использование в подпрограмма *g* ссылается на глобальную *a*.  
  
```  
int a;  
  
void f(int n)   
{  
    a = 0;  
  
    #pragma omp parallel for private(a)  
    for (int i=1; i<n; i++)   
    {  
        a = i;  
        g(i, n);  
        d(a);     // Private copy of "a"  
        ...  
    }  
    ...  
  
void g(int k, int n)   
{  
    h(k,a); // The global "a", not the private "a" in f  
}  
```