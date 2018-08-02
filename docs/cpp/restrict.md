---
title: ограничить | Документация Майкрософт
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3eb361d0b92a3977547388ebfd612915431ec98
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463685"
---
# <a name="restrict"></a>restrict

**Блок, относящийся только к системам Microsoft**

При применении к объявлению или определению функции, возвращающей тип указателя, **ограничить** сообщает компилятору, что функция возвращает объект, который не является *псевдоним*, то есть ссылка на каким-либо другим указатели. Это позволяет компилятору выполнять дополнительные оптимизации.

## <a name="syntax"></a>Синтаксис

> **__declspec(restrict)** *pointer_return_type* *function*();  
  
## <a name="remarks"></a>Примечания

Компилятор распространяет **__declspec(restrict)**. Например, CRT `malloc` функция имеет **__declspec(restrict)** оформления и таким образом, компилятор предполагает, что указатели, инициализированные в расположениях памяти с `malloc` также не используются псевдонимы, ранее существующие указатели.

Компилятор не проверяет, что возвращенный указатель фактически псевдоним не. Это ответственность разработчика, чтобы программа не создавала псевдонимы для указателя, помеченного **ограничить __declspec** модификатор.  
  
Похожую семантику для переменных см. в разделе [__restrict](../cpp/extension-restrict.md).
 
Другую аннотацию, к которому применяется сглаживание внутри функции, см. в разделе [__declspec(noalias)](../cpp/noalias.md).
  
Сведения о **ограничить** ключевое слово, которое является частью C++ AMP, см. в разделе [ограничения (C++ AMP)](../cpp/restrict-cpp-amp.md).  
 
## <a name="example"></a>Пример  

В следующем образце показано использование **__declspec(restrict)**.

Когда **__declspec(restrict)** применяется к функции, что возвращает указатель, это сообщает компилятору, что объем памяти, на которые указывает возвращаемое значение не является псевдонимом. В этом примере указатели `mempool` и `memptr` являются глобальными, поэтому компилятор нельзя быть уверенным, что они ссылаются на память не является псевдонимом. Тем не менее, они используются в `ma` и вызывающий его объект `init` способом, который возвращает памяти, который не в противном случае указывается программой, поэтому **__decslpec(restrict)** позволяет оптимизатору. Это похоже на как заголовки CRT декорировать функции выделения, таких как `malloc` с помощью **__declspec(restrict)** для указания, что они всегда возвращают памяти, который не может быть перенесен, существующие указатели.

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
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
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
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

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также
 [Ключевые слова](../cpp/keywords-cpp.md)  
 [__declspec](../cpp/declspec.md)  
 [__declspec(noalias)](../cpp/noalias.md)  
