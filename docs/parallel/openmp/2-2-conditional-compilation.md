---
title: 2.2 Условная компиляция
ms.date: 11/04/2016
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
ms.openlocfilehash: 9dc107ee9e5328df205d4b6f826f71c23abfb3ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658553"
---
# <a name="22-conditional-compilation"></a>2.2 Условная компиляция

_**OPENMP** имя макроса определяется OpenMP совместимым реализациями как десятичной константы *yyyymm*, она будет называться год и месяц утвержденных спецификации. Этот макрос не должно быть предметом **#define** или **#undef** директивы предварительной обработки.

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

Если поставщиков определяют расширения OpenMP, они могут указать дополнительные предопределенные макросы.