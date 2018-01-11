---
title: "3.1.8 функция omp_get_dynamic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd4ec73b82848efcdface781738639b05a256958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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