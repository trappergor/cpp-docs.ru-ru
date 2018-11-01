---
title: 3.1.6 Функция omp_in_parallel
ms.date: 11/04/2016
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
ms.openlocfilehash: 2f251cb994771278c7f4e3f50f01e02126f6f88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482047"
---
# <a name="316-ompinparallel-function"></a>3.1.6 Функция omp_in_parallel

**Omp_in_parallel** функция возвращает ненулевое значение, если он вызывается в рамках динамического степень параллельной области, выполняя в параллельном режиме; в противном случае возвращает 0. Он следующий:

```
#include <omp.h>
int omp_in_parallel(void);
```

Эта функция возвращает ненулевое значение при вызове из в пределах региона параллельного выполнения, включая вложенные области, которые сериализуются.