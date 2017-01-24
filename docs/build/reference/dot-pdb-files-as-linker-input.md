---
title: "PDB-файлы в качестве входных файлов компоновщика | Microsoft Docs"
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
  - "PDB-файлы, компоновщик - ввод"
  - "PDB-файлы, компоновщик - ввод"
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PDB-файлы в качестве входных файлов компоновщика
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объектные файлы \(OBJ\), скомпилированные с параметром \/Zi, содержат имя базы данных программы \(PDB\).  Имя файла PDB объекта не нужно указывать компоновщику явно; при необходимости программа LINK использует для поиска внедренное имя.  Это также относится к отлаживаемым объектам, содержащимся в библиотеке; файл PDB для отлаживаемой библиотеки должен быть доступен компоновщику вместе с библиотекой.  
  
 Программа LINK также использует файл PDB для хранения отладочной информации файла EXE или DLL.  Файл PDB программы является как входным, так и выходным файлом, поскольку программа LINK обновляет PDB при перепостроении программы.  
  
## См. также  
 [Входные LINK\-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)