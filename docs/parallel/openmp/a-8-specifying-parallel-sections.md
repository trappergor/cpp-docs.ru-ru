---
title: A.8 указание параллельных разделов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d969f1a0e9d9b282104ee00a3b2d06610533ad4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440424"
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Указание параллельных разделов

В следующем примере (для [разделе 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) на странице 14) функции *xaxis*, *ось y*, и *zaxis* могут быть выполнены одновременно. Первый `section` директива является необязательным.  Обратите внимание, что все `section` директивы должна отображаться в лексическую область `parallel sections` построения.

```
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```