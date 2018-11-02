---
title: 3.3.2 Функция omp_get_wtick
ms.date: 11/04/2016
ms.assetid: 1ad08500-bcb0-40d9-a81f-f131819006c9
ms.openlocfilehash: af1e5cf8ef40621342a5162f90cf8c883a59c6a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617962"
---
# <a name="332-ompgetwtick-function"></a>3.3.2 Функция omp_get_wtick

`omp_get_wtick` Функция возвращает значение двойной точности с плавающей запятой, равное количеству секунд между последовательными тактов. Он следующий:

```
#include <omp.h>
double omp_get_wtick(void);
```