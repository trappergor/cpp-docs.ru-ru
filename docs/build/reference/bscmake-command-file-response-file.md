---
title: "Командный файл BSCMAKE (файл отклика) | Microsoft Docs"
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
  - "BSCMAKE - программа, файл команд"
  - "BSCMAKE - программа, файл ответа"
  - "командные файлы"
  - "командные файлы, BSCMAKE - программа"
  - "файлы ответа"
  - "файлы ответа, BSCMAKE - программа"
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Командный файл BSCMAKE (файл отклика)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ввод команд командной строки можно полностью или частично обеспечить с помощью командного файла.  Для задания командного файла используется следующий синтаксис:  
  
```  
BSCMAKE @filename  
```  
  
 Допускается использование только одного командного файла.  Путь можно указать с помощью *filename*.  Перед *filename* необходимо поставить символ @.  BSCMAKE не использует расширения.  После *filename* в командной строке можно указать дополнительные *sbrfiles*.  Командный файл представляет собой текстовый файл, который содержит команды, вводимые в BSCMAKE, в том же порядке, что и при вводе в командной строке.  Аргументы командной строки разделяются одним или несколькими пробелами, символами табуляции или новой строки.  
  
 Следующая команда осуществляет вызов BSCMAKE с помощью командного файла:  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Ниже приведен пример командного файла:  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## См. также  
 [Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)