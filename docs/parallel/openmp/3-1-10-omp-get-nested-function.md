---
title: 3.1.10 функция omp_get_nested | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d019dd757080bbc87ff7aaab1a8745b2a3156b39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392285"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 Функция omp_get_nested

`omp_get_nested` Функция возвращает ненулевое значение, если включен вложенный параллелизм, а значение 0, если она отключена. Дополнительные сведения о вложенных параллелизма см. разделе 3.1.9 на странице 40. Он следующий:

```
#include <omp.h>
int omp_get_nested(void);
```

Если реализация не реализует вложенный параллелизм, эта функция всегда возвращает 0.