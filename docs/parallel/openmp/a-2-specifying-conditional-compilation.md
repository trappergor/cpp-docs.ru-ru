---
title: A.2   Задание условной компиляции
ms.date: 11/04/2016
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
ms.openlocfilehash: 92ae22ffac1b1a1c3fc45a9a7a883203ff6d251e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491225"
---
# <a name="a2---specifying-conditional-compilation"></a>A.2   Задание условной компиляции

Следующие примеры иллюстрируют использование условной компиляции, с помощью макроса OpenMP `_OPENMP` ([раздел 2.2](../../parallel/openmp/2-2-conditional-compilation.md) на странице "8"). При компиляции OpenMP `_OPENMP` становится определен макрос.

```
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

Определенный Оператор препроцессора позволяет более чем один макрос для тестирования одну директиву.

```
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```