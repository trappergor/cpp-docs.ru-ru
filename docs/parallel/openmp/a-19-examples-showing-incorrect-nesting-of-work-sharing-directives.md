---
title: A.19 примеры, показывающие, неправильное вложение директив совместной работы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6778ba61a3367cd4fc90d568508f1a039fd1f7ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691502"
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19   Примеры неправильного вложения директив совместной работы
В этом разделе примерах директив вложенности правила. Дополнительные сведения о директива nesting см. в разделе [разделе 2.9](../../parallel/openmp/2-9-directive-nesting.md) на странице 33.  
  
 Следующий пример является несовместимым из-за внутренней и внешней `for` директивы являются вложенными и выполнить привязку к тому же `parallel` директивы:  
  
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
  
 Следующая версия динамически вложенной в предыдущем примере, также не соответствует требованиям:  
  
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
  
 Следующий пример является несоответствующим из-за `for` и `single` используются вложенные директивы, и они не привязаны к одной и той же параллельной области:  
  
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
  
 Следующий пример является несоответствующим из-за `barrier` директивы внутри `for` может привести к взаимоблокировке:  
  
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
  
 Следующий пример является несоответствующим из-за `barrier` приводит к взаимоблокировке тем, что только один поток за раз можно ввести критической секции:  
  
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
  
 Следующий пример является несоответствующим из-за `barrier` приводит к взаимоблокировке, тем, что только один поток выполняет `single` раздела:  
  
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