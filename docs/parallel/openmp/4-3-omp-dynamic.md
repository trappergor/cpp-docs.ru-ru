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
ms.workload: cplusplus
ms.openlocfilehash: 103067b28990854fb6522c19f4349a9607d65bab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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