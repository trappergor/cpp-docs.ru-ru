---
title: "Пример A.24 закрытый предложения | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: f90a5b49-81ff-4746-ae03-37bbd33f6c08
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f0690f06ac51288605ae4bdd7f12b977f77cf58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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