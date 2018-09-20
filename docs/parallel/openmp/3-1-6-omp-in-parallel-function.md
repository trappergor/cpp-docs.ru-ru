---
title: 3.1.6 функция omp_in_parallel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ba6c35d42f8497869894bd5ec95b83f0c8793f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404622"
---
# <a name="316-ompinparallel-function"></a>3.1.6 Функция omp_in_parallel

**Omp_in_parallel** функция возвращает ненулевое значение, если он вызывается в рамках динамического степень параллельной области, выполняя в параллельном режиме; в противном случае возвращает 0. Он следующий:

```
#include <omp.h>
int omp_in_parallel(void);
```

Эта функция возвращает ненулевое значение при вызове из в пределах региона параллельного выполнения, включая вложенные области, которые сериализуются.