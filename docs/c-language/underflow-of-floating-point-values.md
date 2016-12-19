---
title: "Потеря точности значений с плавающей запятой | Microsoft Docs"
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
  - "C"
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Потеря точности значений с плавающей запятой
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.5.1** Задают ли математические функции значение макроса `ERANGE` для целочисленного выражения `errno` в ошибках диапазона потери точности  
  
 При потере точности числа с плавающей запятой выражение `errno` не получает значения `ERANGE`.  Если значение стремится к нулю и, наконец, теряет значимость, значение устанавливается равным 0.  
  
## См. также  
 [Функции библиотеки](../c-language/library-functions.md)