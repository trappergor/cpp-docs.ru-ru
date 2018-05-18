---
title: 2.2 условная компиляция | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d8c7073548c015d9982b721387176a0ca658c2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="22-conditional-compilation"></a>2.2 Условная компиляция
_**OPENMP** имя макроса определяется OpenMP совместимые реализациями десятичной константы *yyyymm*, которое будет год и месяц утвержденных спецификации. Этот макрос не должно быть субъект **#define** или **#undef** директивы предварительной обработки.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Если поставщиков определяют расширения OpenMP, они могут указать дополнительные предопределенные макросы.