---
title: "Сравнение знаков | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "знаки [C++], сравнение"
  - "сравнение символов"
  - "MBCS [C++], сравнение знаков"
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Сравнение знаков
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Рекомендации:  
  
-   Сравнение известного старшего байта со знаком ASCII выполняется правильно:  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   Для сравнения двух неизвестных знаков требуется использовать один из макросов, определенных в файле Mbstring.h:  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     Это обеспечивает сравнение обоих байтов двухбайтового знака на предмет равенства.  
  
## См. также  
 [Советы по программированию многобайтовой кодировки](../Topic/MBCS%20Programming%20Tips.md)   
 [Переполнение буфера](../text/buffer-overflow.md)