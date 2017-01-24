---
title: "Пути поиска для зависимых элементов | Microsoft Docs"
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
  - "зависимости, NMAKE - программа"
  - "программа NMAKE, зависимости"
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Пути поиска для зависимых элементов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Каждый зависимый элемент имеет дополнительный путь поиска, указанный следующим образом:  
  
## Синтаксис  
  
```  
{directory[;directory...]}dependent  
```  
  
## Примечания  
 NMAKE ищет зависимые элементы в текущей директории, а затем в директориях в указанном порядке.  Макрос указывает часть пути поиска или весь путь поиска.  Заключите имя каталога в фигурные скобки \({ }\); отделите несколько директорий точкой с запятой \(;\).  Знаки табуляции и пробелы запрещены.  
  
## См. также  
 [Зависимые элементы](../build/dependents.md)