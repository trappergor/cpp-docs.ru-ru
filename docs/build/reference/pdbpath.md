---
title: "/PDBPATH | Microsoft Docs"
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
  - "/pdbpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PDB-файлы, путь"
  - "/PDBPATH - параметр (программа dumpbin)"
  - "PDB-файлы, путь"
  - "PDBPATH - параметр (программа dumpbin)"
  - "-PDBPATH - параметр (программа dumpbin)"
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PDBPATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBPATH[:VERBOSE] filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Имя файла DLL или EXE, для которого нужно найти соответствующий файл PDB.  
  
 VERBOSE \(необязательный аргумент\)  
 Перечисление всех каталогов, в которых производится попытка найти файл PDB.  
  
## Заметки  
 При использовании параметра \/PDBPATH поиск производится на компьютере по тем же путям, по которым отладчик искал бы файл PDB; при этом перечисляются все файлы PDB, соответствующие файлу, указанному с помощью аргумента *filename*, если такие файлы будут найдены.  
  
 При использовании отладчика Visual Studio может возникать проблема, связанная с тем, что отладчик использует файл PDB, относящийся к другой версии отлаживаемого файла.  
  
 При использовании параметра \/PDBPATH поиск файлов PDB производится по следующим путям:  
  
-   Проверяется место, где находится исполняемый файл.  
  
-   Проверяется место, где расположен файл PDB, указанный в исполняемом файле.  Обычно это место на момент компоновки образа.  
  
-   Проверяется путь поиска, заданный в интегрированной среде разработки Visual Studio.  
  
-   Проверяются пути из переменных среды \_NT\_SYMBOL\_PATH и \_NT\_ALT\_SYMBOL\_PATH.  
  
-   Возвращение каталога Windows.  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)   
 [\/PDBALTPATH \(использовать альтернативный путь к PDB\-файлу\)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)