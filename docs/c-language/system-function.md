---
title: "Функция system | Microsoft Docs"
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
  - "системная функция"
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Функция system
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.4.5** Содержимое и режим выполнения строки функцией **system**  
  
 Функция **system** выполняет внутреннюю команду операционной системы или файл .EXE, .COM \(.CMD в Windows NT\) или .BAT не из командной строки, а из программы на языке C.  
  
 Функция system находит интерпретатор команд \(обычно это CMD.EXE в Windows NT или COMMAND.COM в Windows\).  Затем функция system передает строку аргумента в интерпретатору команд.  
  
 Дополнительные сведения см. в разделе [system, \_wsystem](../c-runtime-library/reference/system-wsystem.md).  
  
## См. также  
 [Функции библиотеки](../c-language/library-functions.md)