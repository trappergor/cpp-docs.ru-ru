---
title: A.25 примеры предложения атрибута данных copyprivate | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95d68c445c1c20e97725d869061027a9712c2462
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413646"
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   Примеры предложения атрибута данных copyprivate

**Пример 1:** `copyprivate` предложение ([разделе 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) на странице 32) может использоваться для передачи значений, полученных одним потоком непосредственно ко всем экземплярам частных переменных в других потоках.

```
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

Если процедуры *init* вызывается из последовательной региона, его поведение не зависит от наличия директив. После вызова *get_values* процедура выполнена одним потоком, ни один поток покидает конструкция до закрытых объектов, обозначенный *a*, *b*, *x*, и *y* во всех потоках становятся определили со значениями, считанными.

**Пример 2.** в отличие от предыдущего примера, предположим, чтения должна быть выполнена пользователем определенного потока, предположим, что основной поток. В этом случае `copyprivate` предложение нельзя использовать непосредственно сделать вещания, но его можно использовать для предоставления доступа к общей временный объект.

```
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**Пример 3.** Предположим, что количество блокировок объектов, необходимых внутри параллельной области невозможно легко определить перед вводом. `copyprivate` Предложение может использоваться для предоставления доступа к объектам совмещаемую блокировку, которые назначаются в направлении, область параллельной обработки.

```
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```