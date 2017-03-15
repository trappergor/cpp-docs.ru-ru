---
title: "2.4.3 single Construct | Microsoft Docs"
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
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.4.3 single Construct
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Одинарный** директива задает конструкцию, которая указывает, что связанный структурированном блоке выполняется только одним потоком в рабочей группе \(не обязательно\) главном потоке.  Синтаксис  **Одинарный** директива выглядит следующим образом:  
  
```  
#pragma omp single [clause[[,] clause] ...] new-line  
   structured-block  
```  
  
 Предложение одно из следующих действий:  
  
 **private \(**список переменных**\)**  
  
 **\(firstprivate**список переменных**\)**  
  
 **\(copyprivate**список переменных**\)**  
  
 **nowait**  
  
 Неявный барьера после **Одинарный** конструкция, если a  **nowait** предложение distinct.  
  
 Ограничения **Одинарный** директива выглядит следующим образом:  
  
-   Только одного **nowait** предложение может отображаться на a  **Одинарный** директива.  
  
-   **copyprivate** предложение следует использовать с  **nowait** предложение.  
  
## Перекрестные ссылки:  
  
-   **private**"  **firstprivate**и  **copyprivate** предложения см. в разделе  [Раздел 2.7.2](../Topic/2.7.2%20Data-Sharing%20Attribute%20Clauses.md) на странице 25.