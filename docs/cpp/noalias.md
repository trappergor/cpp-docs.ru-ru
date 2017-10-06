---
title: "noalias | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: cb8d3425b08984f31954df3a7cf7771e85301a5b
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="noalias"></a>noalias

**Блок, относящийся только к системам Майкрософт**

`noalias`означает, что вызов функции не изменять или ссылаться на видимое глобальное состояние и изменяет памяти, на который указывает только *непосредственно* параметры-указатели (косвенные обращения первого уровня).

Если функция отмечена как `noalias`, оптимизатор может считать, что, помимо самих параметров, внутри функции используются или изменяются только косвенные обращения первого уровня для параметров-указателей. Видимое глобальное состояние — это набор всех данных, который не определяются и на которые нет ссылок за пределами области компиляции, и адрес которых не берется. Область компиляции — все исходные файлы ([/LTCG (Создание кода во время компоновки)](../build/reference/ltcg-link-time-code-generation.md) сборок) или единый исходный файл (отличных**/LTCG** сборки).

## <a name="example"></a>Пример

В следующем примере показано использование `__declspec(restrict)` и `__declspec(noalias)`. Как правило, возвращаемая память из `malloc` — `restrict` поскольку заголовки CRT декорированы соответствующим образом.

Однако в этом примере указатели `mempool` и `memptr` являются глобальными, поэтому компилятор не имеет гарантии, память не подвергается выравниванию. Если декорировать функции, которые возвращают указатели, с помощью `__declspec(restrict)`, то компилятор будет знать, что память, на которую указывает возвращенное значение, не выравнивается.

В этом примере декорирование функции, которая обращается к памяти, с помощью `__declspec(noalias)` сообщает компилятору, что эта функция может влиять на глобальное состояние только через указатели из своего списка параметров.

```C
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

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)  
[Ключевые слова](../cpp/keywords-cpp.md)
