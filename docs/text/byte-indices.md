---
title: "Индексы байтов | Microsoft Docs"
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
helpviewer_keywords: 
  - "индексы байтов [C++]"
  - "MBCS [C++], индексы байтов"
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Индексы байтов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Рекомендации:  
  
-   Работа с побайтовым индексом в строке может вызвать проблемы, аналогичные проблемам, которые возникают при манипуляциях указателем.  Рассмотрим пример, в котором выполняется просмотр строки на наличие знаков обратной косой черты:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     Это может быть индексом младшего байта, а не старшего байта, и поэтому не может указывать на `character`.  
  
-   Используйте функцию [\_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md), чтобы разрешить предыдущую проблему:  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     Этот пример правильно индексирует первый байт, и поэтому и `character`.  Функция `_mbclen` определяет размер знака \(1 или 2 байта\).  
  
## См. также  
 [Советы по программированию многобайтовой кодировки](../Topic/MBCS%20Programming%20Tips.md)   
 [Последний символ в строке](../text/last-character-in-a-string.md)