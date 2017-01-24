---
title: "3.1.10 omp_get_nested Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.10 omp_get_nested Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_nested` функция возвращает ненулевое значение, если включена вложенные параллелизм и 0, если она блокируется.  Дополнительные сведения о вложенных параллелизма см. в разделе 3.1.9 на странице 40.  Формат следующий:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Если реализация не реализует вложенных параллелизм, то функция всегда возвращает 0.