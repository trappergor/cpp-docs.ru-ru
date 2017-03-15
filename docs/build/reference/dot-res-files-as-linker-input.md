---
title: "RES-файлы в качестве входных файлов компоновщика | Microsoft Docs"
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
  - "RES-файлы в качестве входных файлов компоновщика"
  - "связывание [C++], файлы ресурсов"
  - "RES-файлы в качестве входных файлов компоновщика"
  - "файлы ресурсов, связывание"
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# RES-файлы в качестве входных файлов компоновщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

При компоновке программы можно указать RES\-файл.  RES\-файл создается компилятором ресурсов \(RC\).  Программа LINK автоматически преобразует RES\-файлы в формат COFF.  Инструмент CVTRES.exe должен находиться в том же каталоге, что и LINK.exe, или в каталоге, заданном в переменной среды PATH.  
  
## См. также  
 [Входные LINK\-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)