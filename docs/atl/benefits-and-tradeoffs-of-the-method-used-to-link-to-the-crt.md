---
title: "Benefits and Tradeoffs of the Method Used to Link to the CRT | Microsoft Docs"
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
  - "_ATL_MIN_CRT - макрос"
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Benefits and Tradeoffs of the Method Used to Link to the CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Проект может связать с CRT или статически или динамически.  Таблица под структурами преимущества и уступки включенной в разделе выбрать, какой метод нужно использовать.  
  
|Метод|Преимущество|Придется соблюдать баланс|  
|-----------|------------------|-------------------------------|  
|Статической компоновке на CRT<br /><br /> \(**Библиотека времени выполнения** присваивается **Single\-threaded**\)|Библиотека DLL CRT не требуется в системе, где образа выполняется.|О 25K запускаемых кода добавляется к вашему образу, по существу увеличить ее размер.|  
|Динамическое связывание на CRT<br /><br /> \(**Библиотека времени выполнения** присваивается **Многопоточная**\)|Этот способ не требует кода запуска CRT, поэтому он намного меньше.|Библиотека DLL CRT, должно находиться в системе, запущенных образа.|  
  
 Раздел [Связывание с CRT в проекте библиотеки ATL](../atl/linking-to-the-crt-in-your-atl-project.md) содержит сведения о том, как выбрать способ связывания с CRT.  
  
## См. также  
 [Программирование с использованием ATL и кода среды выполнения C](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Поведение библиотеки времени выполнения](../build/run-time-library-behavior.md)   
 [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)