---
title: "Использование макроса NMAKE | Microsoft Docs"
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
  - "макросы, NMAKE - программа"
  - "макрос (NMAKE), использование"
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Использование макроса NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Чтобы использовать макрос, следует заключить его имя в круглые скобки и указать в начале знак доллара \("$"\).  
  
## Синтаксис  
  
```  
$(macroname)  
```  
  
## Примечания  
 Пробелы не разрешаются.  Если имя макроса *macroname* представляет собой одиночный знак, то круглые скобки необязательны.  Строка определения будет подставлена вместо последовательности $\(*macroname*\); неопределенный макрос заменяется пустой строкой.  
  
## Дополнительные сведения  
 [Макроподстановка](../build/macro-substitution.md)  
  
## См. также  
 [Макросы и программа NMAKE](../Topic/Macros%20and%20NMAKE.md)