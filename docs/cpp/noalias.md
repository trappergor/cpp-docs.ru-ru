---
title: "noalias | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "noalias"
  - "noalias_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], noalias"
  - "noalias __declspec - ключевое слово"
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# noalias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 `noalias` означает, что вызов функции не изменяет видимое глобальное состояние и не ссылается на него; изменения производятся только в памяти, на которую непосредственно \(`directly`\) указывают параметры\-указатели \(косвенные обращения первого уровня\).  
  
 Если функция отмечена как `noalias`, оптимизатор может считать, что, помимо самих параметров, внутри функции используются или изменяются только косвенные обращения первого уровня для параметров\-указателей.  Видимое глобальное состояние — это набор всех данных, который не определяются и на которые нет ссылок за пределами области компиляции, и адрес которых не берется.  Область компиляции — это все файлы исходного кода \(сборки [Параметр \/LTCG \(создание кода во время компоновки\)](../build/reference/ltcg-link-time-code-generation.md)\) или один файл исходного кода \(сборки, не являющиеся сборками **\/LTCG**\).  
  
## Пример  
 В следующем примере показано использование `__declspec(restrict)` и `__declspec(noalias)`.  Обычно память, возвращаемая вызовом `malloc`, является `restrict` и `noalias`, поскольку заголовки CRT декорированы соответствующим образом.  
  
 Однако в этом примере указатели `mempool` и `memptr` являются глобальными, поэтому компилятор не имеет гарантии, что память не подвергается выравниванию.  Если декорировать функции, которые возвращают указатели, с помощью `__declspec(restrict)`, то компилятор будет знать, что память, на которую указывает возвращенное значение, не выравнивается.  
  
 В этом примере декорирование функции, которая обращается к памяти, с помощью `__declspec(noalias)` сообщает компилятору, что эта функция может влиять на глобальное состояние только через указатели из своего списка параметров.  
  
```  
// declspec_noalias.c   
#include <stdio.h>  
#include <stdlib.h>  
  
#define M 800  
#define N 600  
#define P 700  
  
float * mempool, * memptr;  
  
__declspec(restrict) float * ma(int size)  
{  
    float * retval;  
    retval = memptr;  
    memptr += size;  
    return retval;  
}  
  
__declspec(restrict) float * init(int m, int n)  
{  
    float * a;  
    int i, j;  
    int k=1;  
  
    a = ma(m * n);  
    if (!a) exit(1);  
    for (i=0; i<m; i++)  
        for (j=0; j<n; j++)  
            a[i*n+j] = 0.1/k++;  
    return a;  
}  
  
__declspec(noalias) void multiply(float * a, float * b, float * c)  
{  
    int i, j, k;  
  
    for (j=0; j<P; j++)  
        for (i=0; i<M; i++)  
            for (k=0; k<N; k++)  
                c[i * P + j] =   
                          a[i * N + k] *   
                          b[k * P + j];  
}  
  
int main()  
{  
    float * a, * b, * c;  
  
    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));  
  
    if (!mempool)   
    {  
        puts("ERROR: Malloc returned null");  
        exit(1);  
    }  
  
    memptr = mempool;  
    a = init(M, N);  
    b = init(N, P);  
    c = init(M, P);  
  
    multiply(a, b, c);  
}  
```  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)