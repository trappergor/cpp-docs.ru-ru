---
title: "A.20   Binding of barrier Directives | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.20   Binding of barrier Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Директивы вызов правил привязки, a **барьер** директива, который необходимо привязать к ближайший заключать  `parallel` директива.  Дополнительные сведения о привязке см. в разделе директивной [Раздел 2.8](../../parallel/openmp/2-8-directive-binding.md) на странице 32.  
  
 В следующем примере вызов от Главная В sub2 уступчивы поскольку **барьер** \(в sub3привязывает в параллельной области внутри\) sub2.  Вызов от Главная В sub1 уступчивы поскольку **барьер** привязывает в параллельной области в процедуре sub2.  Вызов от Главная В sub3 уступчивы поскольку **барьер** не привязан к любой параллельной области и игнорирует.  Также обратите внимание, что **барьер** синхронизировать только команда потоков во включающем параллельной области, а не всех потоков, созданных в пределах sub1.  
  
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