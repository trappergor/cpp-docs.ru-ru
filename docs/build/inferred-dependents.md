---
title: "Выводимые зависимости | Microsoft Docs"
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
  - "зависимости, выводимый"
  - "выводимые зависимости (NMAKE)"
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Выводимые зависимости
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выводимая зависимость выводится по правилу вывода и оценивается перед явными зависимостями.  Если выводимая зависимость устарела по сравнению с соответствующим ей целевым объектом, то программа NMAKE вызывает для этой зависимости блок команд.  Если выводимая зависимость не существует или устарела по отношению к собственным зависимостям, программа NMAKE сначала обновляет эту зависимость.  Дополнительные сведения о выводимых зависимостях см. в разделе [Правила вывода](../build/inference-rules.md).  
  
## См. также  
 [Зависимые элементы](../build/dependents.md)