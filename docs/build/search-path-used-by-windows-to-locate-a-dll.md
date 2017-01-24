---
title: "Путь поиска, используемый Windows для обнаружения библиотеки DLL | Microsoft Docs"
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
  - "DLL-библиотеки [C++], Windows - путь поиска"
  - "поиск библиотек DLL"
  - "известные поиски DLL [C++]"
  - "расположение библиотек DLL"
  - "пути поиска [C++]"
  - "поиск [C++], библиотеки DLL"
  - "Windows [C++], пути поиска DLL"
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Путь поиска, используемый Windows для обнаружения библиотеки DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Используя механизмы явного и неявного связывания, Windows сначала выполняет поиск "известных библиотек DLL", таких как Kernel32.dll и User32.dll.  Затем Windows выполняет поиск библиотек DLL в следующей последовательности:  
  
1.  Каталог, в котором находится исполняемый модуль текущего процесса.  
  
2.  Текущий каталог.  
  
3.  Системный каталог Windows.  Путь к этому каталогу извлекается с помощью функции **GetSystemDirectory**.  
  
4.  Каталог Windows.  Путь к этому каталогу извлекается с помощью функции **GetWindowsDirectory**.  
  
5.  Каталоги, указанные в переменной среды PATH.  
  
    > [!NOTE]
    >  Переменная среды LIBPATH не используется.  
  
## Выберите действие.  
  
-   [Неявное связывание](../Topic/Linking%20Implicitly.md)  
  
-   [Явное связывание](../build/linking-explicitly.md)  
  
-   [Определение подходящего метода связывания](../build/determining-which-linking-method-to-use.md)  
  
## См. также  
 [DLL в Visual C\+\+](../build/dlls-in-visual-cpp.md)