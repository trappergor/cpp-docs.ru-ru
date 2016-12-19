---
title: "3.1.6 omp_in_parallel Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.6 omp_in_parallel Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Omp\_in\_parallel функция возвращает ненулевое значение, если она вызывается в пределах динамической экстенты параллельной области при выполнении в параллельном режиме. в противном случае возвращается 0.  Формат следующий:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Эта функция возвращает ненулевое значение вызывается из области, выполняемых параллельно, включая вложенные области, которые будут сериализованы.