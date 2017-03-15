---
title: "EXP-файлы в качестве входных файлов компоновщика | Microsoft Docs"
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
  - "EXP-файлы [C++]"
  - "EXP-файлы"
  - "данные - экспортирование, EXP-файлы - экспорт"
  - "функции - экспортирование"
  - "функции - экспортирование, экспортируемые функции - информация"
  - "функции [C++], экспорт"
  - "библиотеки - импорт, компоновочные файлы"
  - "связывание [C++], экспорты"
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EXP-файлы в качестве входных файлов компоновщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Файлы экспорта \(EXP\) содержат сведения об экспортируемых функциях и элементах данных.  Когда программа LIB создает библиотеку импорта, она также создает и EXP\-файл.  EXP\-файл используется при компоновке программ, которые как экспортируют, так и импортируют объекты другой программы косвенно или напрямую.  При компоновке с EXP\-файлом программа LINK не создает библиотеку импорта, поскольку она предполагает, что программа LIB уже ее создала.  Дополнительные сведения о EXP\-файлах и библиотеках импорта см. в разделе [Работа с библиотеками импорта и файлами экспорта](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## См. также  
 [Входные LINK\-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)