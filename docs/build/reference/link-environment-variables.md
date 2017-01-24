---
title: "Переменные среды инструмента LINK | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "переменные среды [C++], LINK"
  - "LIB - переменная среды"
  - "LINK - средство [C++], переменные среды"
  - "переменные, среда"
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Переменные среды инструмента LINK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Средство LINK использует следующие переменные среды:  
  
-   LINK и \_LINK\_, если они определены.  LINK добавляет параметры и аргументы, заданные в переменной среды компилятора LINK, в начало параметров и аргументов командной строки и добавляет параметры и аргументы, заданные в \_LINK\_, в конец аргументов командной строки перед обработкой.  
  
-   LIB, если определено.  Средство LINK использует путь LIB при поиске объекта, библиотеки или другого файла, указанного в командной строке, или использует параметр [\/BASE](../../build/reference/base-base-address.md).  Средство также использует путь LIB для поиска PDB\-файла, указанного в объекте.  Переменная LIB может содержать один или несколько путей, разделенных точкой с запятой.  Один путь должен указывать на подкаталог \\lib папки установки Visual C\+\+.  
  
-   PATH, если средству необходимо запускать программу CVTRES и не удается найти файл в том же каталоге, где находится LINK.  \(CVTRES необходима LINK для связи с RES\-файлом.\) Переменная PATH должна указывать на подкаталог \\bin папки установки Visual C\+\+.  
  
-   TMP для указания каталога при связывании OMF или RES\-файлов.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Установка переменных пути и среды при построении из командной строки](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)