---
title: "2.6.1 конструкция-шаблоны | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bff566967749068f9792a98dc3cf2151e4df3d9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="261-master-construct"></a>2.6.1 Конструкция master
**Master** директива идентифицирует конструкцию, которая определяет структурированный блок, который выполняется потоком главной рабочей группы. Синтаксис **master** директивы таков:  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 Другие потоки в группе не выполняйте структурированных блоку. Нет подразумеваемых барьера на запись или выход из конструкция master не существует.