---
title: A.24   Примеры предложения private
ms.date: 11/04/2016
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
ms.openlocfilehash: facf5b953b26d284f6bfed4f35a9162f6d2bf212
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552962"
---
# <a name="a24---example-of-the-private-clause"></a>A.24   Примеры предложения private

`private` Предложение ([разделе 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) на стр. 25) из параллельной области действует только лексической области региона, но не для динамического экстент области.  Таким образом, в следующем примере, любое использование переменной *a* в `for` цикла в подпрограмме *f* ссылается на частную копию *a*, а использование в подпрограмма *g* ссылается на глобальную *a*.

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