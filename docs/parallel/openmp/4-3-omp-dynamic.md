---
title: "4.3 OMP_DYNAMIC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b23719d1559a00b807f724a3e31eb7b673a5a17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
**OMP_DYNAMIC** переменной среды, включает или отключает динамическую настройку количество потоков для выполнения параллельных областей, если только явным образом включен или отключен путем вызова динамическуюнастройку**omp_set_dynamic** библиотечная процедура. Это значение должно быть **TRUE** или **FALSE**.  
  
 Если значение **TRUE**, число потоков, используемых для выполнения параллельных области могут быть адаптированы, среда выполнения, лучше всего использовать системные ресурсы.  Если значение **FALSE**, динамическую настройку отключена. Условие по умолчанию определяется реализацией.  
  
 Пример  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>Перекрестные ссылки:  
  
-   Дополнительные сведения о параллельных регионов см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **omp_set_dynamic** см. в разделе [раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.