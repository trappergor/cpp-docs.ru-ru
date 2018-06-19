---
title: Привязка A.20 директив барьера | Документы Microsoft
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
ms.openlocfilehash: b1123ab0b4d406a613176dfcd50f459d089e45d9
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691418"
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