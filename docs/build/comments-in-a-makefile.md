---
title: "Комментарии в файлах makefile | Microsoft Docs"
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
  - "makefile - файлы, комментарии"
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Комментарии в файлах makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Комментарии должны предваряться знаком номера \(\#\).  Программа NMAKE не обрабатывает текст, следующий за знаком номера до следующего знака новой строки.  Примеры  
  
```  
# Comment on line by itself  
OPTIONS = /MAP  # Comment on macro definition line  
  
all.exe : one.obj two.obj  # Comment on dependency line  
    link one.obj two.obj  
# Comment in commands block  
#   copy *.obj \objects  # Command turned into comment  
    copy one.exe \release  
  
.obj.exe:  # Comment on inference rule line  
    link $<  
  
my.exe : my.obj ; link my.obj  # Err: cannot comment this  
 # Error: # must be the first character  
.obj.exe: ; link $<  # Error: cannot comment this  
```  
  
 Чтобы задать литерал, соответствующий знаку номера, вставьте перед ним знак крышки \(**^**\):  
  
```  
DEF = ^#define  #Macro for a C preprocessing directive  
```  
  
## См. также  
 [Содержимое файла makefile](../build/contents-of-a-makefile.md)