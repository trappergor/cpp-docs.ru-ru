---
title: "Неустранимая ошибка NMAKE U1064 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1064"
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка NMAKE U1064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MAKEFILE не найден и конечный файл не задан  
  
 В командной строке программы NMAKE не задан файл makefile или целевой объект, при этом в текущем каталоге файл MAKEFILE отсутствует.  
  
 В программе NMAKE необходимо задать файл makefile или целевой объект командной строки \(или оба объекта\).  Чтобы обеспечить доступность файла makefile для программы NMAKE, задайте параметр \/F или поместите файл с именем MAKEFILE в текущий каталог.  Если файл makefile не задан, целевой объект командной строки может создаваться в программе NMAKE с использованием правила вывода.