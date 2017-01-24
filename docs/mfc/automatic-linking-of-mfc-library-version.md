---
title: "Автоматическая компоновка версии библиотеки MFC | Microsoft Docs"
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
  - "defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "автоматические ссылки [C++]"
  - "defaultlib в MFC"
  - "связывание [C++]"
  - "связывание [C++], автоматически версии библиотеки MFC"
  - "связывание [C++], MFC"
  - "MFC - библиотеки, связывание с"
  - "MFC - библиотеки, версии"
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Автоматическая компоновка версии библиотеки MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В версиях до версии MFC 3.0 \(до версии Visual C\+\+ 2.0 C\), необходимо вручную определить правильную версию библиотеки MFC в списке ввода библиотек для компоновщика.  Начиная с версии MFC 3.0 и более поздних версиях, больше не требуется вручную указать версию библиотеки MFC.  Вместо этого файлы заголовков MFC автоматически определяют правильную версию библиотеки MFC, в зависимости от значений, указанных с `#define`, например **\_DEBUG** или **\_UNICODE**.  Файлы заголовков MFC добавляют директивы **\/defaultlib** инструктируя компоновщик связывание в определенной версии библиотеки MFC.  
  
 Например, следующий фрагмент кода из файла заголовка AFX.H указывает компоновщик или связь в версии NAFXCWD.LIB или NAFXCW.LIB MFC, в зависимости от того, используется ли отладочной версии MFC.  
  
 `#ifndef _UNICODE`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "nafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "nafxcw.lib")`  
  
 `#endif`  
  
 `#else`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "uafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "uafxcw.lib")`  
  
 `#endif`  
  
 `#endif`  
  
 Файлы заголовков MFC также связывают во всех необходимых библиотек, включая библиотеки MFC, библиотеки Win32, OLE библиотеки OLE, библиотеки, сформированного из примеров, библиотеки ODBC и т д  Библиотеки Win32. Kernel32.Lib, User32.Lib и GDI32.Lib.  
  
## См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)