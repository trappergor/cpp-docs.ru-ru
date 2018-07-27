---
title: 3.1.8 функция omp_get_dynamic | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af7755173ab884a40a5f8a41f432f265cc1e6c32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686195"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 Функция omp_get_dynamic
**Omp_get_dynamic** функция возвращает ненулевое значение, если включено динамическое выравнивание потоков и возвращает 0 в противном случае. Он следующий:  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Если реализация не реализует динамическую настройку число потоков, эта функция всегда возвращает 0.  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   Описание настройки динамического потока см. [раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.