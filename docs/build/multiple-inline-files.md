---
title: "Использование нескольких встроенных файлов | Microsoft Docs"
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
  - "встроенные файлы, несколько (NMAKE)"
  - "несколько встроенных файлов"
  - "программа NMAKE, встроенные файлы"
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Использование нескольких встроенных файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Команда может создавать несколько встроенных файлов.  
  
## Синтаксис  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## Заметки  
 Для каждого файла следует указать одну или несколько строк встроенного текста, за которым следует закрывающая строка, содержащая разделитель.  Необходимо начать текст второго файла со строки, следующей за разделяющей строкой первого файла.  
  
## См. также  
 [Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)