---
title: "Привязка A.20 директив барьера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b8cc2799f0aea9e75b3aad44d3cfa9e3f5e7de4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="a20---binding-of-barrier-directives"></a>A.20   Привязка директив barrier
Привязка директив правила вызова для **барьера** директивы для привязки к ближайшей окружению `parallel` директивы. Дополнительные сведения о директиве привязки см. в разделе [2.8 разделе](../../parallel/openmp/2-8-directive-binding.md) на стр.  
  
 В следующем примере вызов из *основной* для *sub2* является совместимым поскольку **барьера** (в *sub3*) привязывается к параллельной области в *sub2*. Вызов из *основной* для *sub1* является совместимым поскольку **барьера** привязывается к параллельной области в подпрограмме *sub2*.  Вызов из *основной* для *sub3* является совместимым поскольку **барьера** не привязывается к любой параллельной области и учитывается. Также Обратите внимание, что **барьера** синхронизирует только команда потоков в области включающего параллельных и не все потоки, созданные в *sub1*.  
  
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