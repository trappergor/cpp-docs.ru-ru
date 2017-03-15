---
title: "Поддержка библиотек динамической компоновки | Microsoft Docs"
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
  - "DLL-библиотеки [C++], MFC - библиотека"
  - "библиотеки DLL MFC [C++], обычные библиотеки DLL"
  - "NAFXDW.LIB"
  - "NAFXDWD.LIB"
  - "обычные библиотеки DLL [C++], целевые объекты проекта в виде DLL-библиотек"
  - "библиотеки USRDLL, поддержка DLL"
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Поддержка библиотек динамической компоновки
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотеки NAFXCW.lib и NAFXCWD.lib \(перечислены в таблице соглашений об именовании статических библиотек в [Соглашения об именовании библиотек](../Topic/Library%20Naming%20Conventions.md)\) создает в проекте как вызванная библиотеки динамической компоновки \(DLL\) «обычная библиотека DLL» \(ранее «USRDLL»\), который можно использовать с приложениями, разработанными не с библиотекой классов.  Эта поддержка библиотеки DLL отличается от MFCx0.dll и MFCx0D.DLL \(называемых AFXDLL\), который содержит все библиотеки классов в библиотеке DLL.  Дополнительные сведения см. в разделе [DLLs](../build/dlls-in-visual-cpp.md).  Для таблицы имен библиотеки DLL см. в разделе [Соглашения об именовании библиотек DLL MFC](../build/naming-conventions-for-mfc-dlls.md).  
  
## См. также  
 [Версии библиотек MFC](../mfc/mfc-library-versions.md)