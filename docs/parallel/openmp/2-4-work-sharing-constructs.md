---
title: "2.4 Work-sharing Constructs | Microsoft Docs"
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
ms.assetid: 25bb4ded-8466-4daa-a863-766b5a99b995
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4 Work-sharing Constructs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Рабочий\-совместно с помощью конструкции распределяет выполнение соответствующей выписки члены группы, которые встречаются среди его.  Рабочий\-совместно с помощью директивы не запустятся новых потоков, и неявный барьера для записи в рабочий\-совместно с помощью конструкций.  
  
 Последовательность рабочий\-совместно с помощью конструкций и **барьер** обнаружены рекомендации должны быть одинаковыми для каждого потока в рабочей группе.  
  
 OpenMP определяет следующие рабочий\-совместно с помощью конструкции, которые описаны в разделах, выполните:  
  
-   **для** директива  
  
-   **Разделы** директива  
  
-   **Одинарный** директива