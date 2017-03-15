---
title: "A.19   Examples Showing Incorrect Nesting of Work-sharing Directives | Microsoft Docs"
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
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.19   Examples Showing Incorrect Nesting of Work-sharing Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Примеры в этом разделе демонстрируют директивные правила вложения.  Дополнительные сведения о вложении см. в разделе директивном [Раздел 2.9](../../parallel/openmp/2-9-directive-nesting.md) на странице 33.  
  
 В следующем примере noncompliant поскольку внутренняя и outer `for` правила являются вложенными и связываются с одинаковым  `parallel` директива:  
  
```  
void wrong1(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
      int i, j;  
      #pragma omp for  
      for (i=0; i<n; i++) {  
          #pragma omp for  
              for (j=0; j<n; j++)  
                 work(i, j);  
     }  
   }  
}  
```  
  
 Следующая динамически вложенных версия предыдущего примера также noncompliant:  
  
```  
void wrong2(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++)  
        work1(i, n);  
  }  
}  
  
void work1(int i, int n)  
{  
  int j;  
  #pragma omp for  
    for (j=0; j<n; j++)  
      work2(i, j);  
}  
```  
  
 В следующем примере noncompliant поскольку `for` и  `single` правила являются вложенными, они привязываются к одной и той же параллельной области:  
  
```  
void wrong3(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        #pragma omp single  
          work(i);  
      }  
  }  
}  
```  
  
 В следующем примере noncompliant поскольку a `barrier` директива in a  `for` может привести к взаимоблокировке.  
  
```  
void wrong4(int n)  
{  
  #pragma omp parallel default(shared)  
  {  
    int i;  
    #pragma omp for  
      for (i=0; i<n; i++) {  
        work1(i);  
        #pragma omp barrier  
        work2(i);  
      }  
  }  
}  
```  
  
 В следующем примере noncompliant поскольку `barrier` результаты взаимоблокировке из\-за факту, что одновременно только один поток может ввести критическую секцию.  
  
```  
void wrong5()  
{  
  #pragma omp parallel  
  {  
    #pragma omp critical  
    {  
       work1();  
       #pragma omp barrier  
       work2();  
    }  
  }  
}  
```  
  
 В следующем примере noncompliant поскольку `barrier` результаты взаимоблокировке из\-за факту которому только один поток выполнения  `single` раздел:  
  
```  
void wrong6()  
{  
  #pragma omp parallel  
  {  
    setup();  
    #pragma omp single  
    {  
      work1();  
      #pragma omp barrier  
      work2();  
    }  
    finish();  
  }  
}  
```