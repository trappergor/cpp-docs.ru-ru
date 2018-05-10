---
title: 2.6.1 конструкция-шаблоны | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a60a8df380fdcc0052d8fe2d070c8d926bcb28f8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="261-master-construct"></a>2.6.1 Конструкция master
**Master** директива идентифицирует конструкцию, которая определяет структурированный блок, который выполняется потоком главной рабочей группы. Синтаксис **master** директивы таков:  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 Другие потоки в группе не выполняйте структурированных блоку. Нет подразумеваемых барьера на запись или выход из конструкция master не существует.