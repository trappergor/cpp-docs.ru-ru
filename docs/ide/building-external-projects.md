---
title: "Построение внешних проектов | Microsoft Docs"
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
  - "построения [C++], внешние проекты"
  - "внешние проекты"
  - "Проекты, использующие файл makefile, внешние проекты"
  - "проекты [C++], внешние проекты"
  - "проекты Visual C++, внешние проекты"
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Построение внешних проектов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Внешний проект — это проект Visual C\+\+, использующий файл makefile или иные средства, не входящие в среду разработки Visual C\+\+ \(внешние по отношению к ней\).  
  
 Если в среде разработки Visual C\+\+ необходимо выполнить построение внешнего проекта \(например, проекта makefile\), следует создать проект Makefile и указать команду построения и выходной файл проекта в мастере приложений Makefile.  Дополнительные сведения см. в разделе [Создание проекта Makefile](../ide/creating-a-makefile-project.md).  
  
 Обратите внимание, что Visual C\+\+ больше не поддерживает возможность экспорта файла makefile активного проекта из среды разработки.  Для построения проектов Visual Studio с помощью командной строки используйте [параметры командной строки для команды Devenv](../Topic/Devenv%20Command%20Line%20Switches.md).  
  
## См. также  
 [Построение проектов C\+\+ в Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)