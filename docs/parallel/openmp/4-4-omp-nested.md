---
title: 4.4 OMP_NESTED | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1779b75774a2177a0d6a4f0661406e28b479a7ee
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED` Переменной среды, включает или отключает вложенный параллелизм, если не включен или отключен, вызвав вложенный параллелизм `o` **mp_set_nested** библиотечная процедура. Если значение **TRUE**, вложенный параллелизм включена; Если задано значение **FALSE**вложенного параллелизм отключен. Значение по умолчанию — **FALSE**.  
  
 Пример  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>Перекрестная ссылка:  
  
-   `omp_set_nested` см. в разделе [раздел 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) на странице 40.