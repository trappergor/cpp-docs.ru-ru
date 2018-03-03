---
title: "2.2 условная компиляция | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fb58458710c18f89f4057061b9c67b4eef1bbf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="22-conditional-compilation"></a>2.2 Условная компиляция
_**OPENMP** имя макроса определяется OpenMP совместимые реализациями десятичной константы *yyyymm*, которое будет год и месяц утвержденных спецификации. Этот макрос не должно быть субъект **#define** или **#undef** директивы предварительной обработки.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Если поставщиков определяют расширения OpenMP, они могут указать дополнительные предопределенные макросы.