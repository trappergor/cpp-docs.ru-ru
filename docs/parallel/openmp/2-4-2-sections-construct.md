---
title: "2.4.2 sections Construct | Microsoft Docs"
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
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.2 sections Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Разделы** директива указывает безитерационную рабочий\-совместно, используя конструкцию, которая определяет набор конструкций, которые должны быть разделенным между потоками в рабочей группе.  Каждый шаг выполняется один раз потоком в рабочей группе.  Синтаксис  **Разделы** директива выглядит следующим образом:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-line  
      structured-block ]  
...  
}  
```  
  
 Предложение одно из следующих действий:  
  
 **private \(**список переменных**\)**  
  
 **\(firstprivate**список переменных**\)**  
  
 **\(lastprivate**список переменных**\)**  
  
 **снижение \(**Оператор**.** список переменных**\)**  
  
 **nowait**  
  
 Каждый раздел предшествует a **раздел** однако директива  **раздел** дополнительная директива для первого раздела.  **раздел** рекомендации должны появляться в лексической области памяти  **Разделы** директива.  Неявный барьера в конце a **Разделы** конструкция, если набор узлов a  **nowait** указывает.  
  
 Ограничения **Разделы** директива выглядит следующим образом:  
  
-   A **раздел** директива не должна использоваться вне лексической области памяти  **Разделы** директива.  
  
-   Только одного **nowait** предложение может отображаться на a  **Разделы** директива.  
  
## Перекрестные ссылки:  
  
-   **private**"  **firstprivate**"  **lastprivate**и  **сокращение** предложения см. в разделе  [Раздел 2.7.2](../Topic/2.7.2%20Data-Sharing%20Attribute%20Clauses.md) на странице 25.