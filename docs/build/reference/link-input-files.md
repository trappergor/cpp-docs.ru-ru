---
title: "Входные LINK-файлы | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "ввод команд - файлы компоновщика [C++]"
  - "файлы [C++], LINK"
  - "библиотеки - импорт [C++], компоновочные файлы"
  - "входные файлы [C++], LINK"
  - "LINK - средство [C++], входные файлы"
  - "компоновщик [C++], входные файлы"
  - "файлы определения модулей"
  - "файлы определения модулей, компоновочные файлы"
  - "ресурсы [C++], компоновочные файлы"
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Входные LINK-файлы
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Был предоставлен компоновщик с файлами, содержащими объекты, импортируемые и стандартные библиотеки, источники, определения модулей и ввод команд.  LINK не использует расширения файлов для создания предположений о содержимом файла.  Вместо этого LINK проверяет каждый входящий файл для того, чтобы определить тип файлов.  
  
 Объектные файлы в командной строке выполняются в том порядке, в котором они появляются в командной строке.  Поиск библиотек в командной строке осуществляется в следующем порядке, с использованием следующих механизмов: Неразрешенные символы при связывании в объектный файл библиотек ищутся в списке библиотек, затем в следующих библиотеках из командной строки и директивах [\/DEFAULTLIB \(определение библиотеки по умолчанию\)](../../build/reference/defaultlib-specify-default-library.md), и затем во всех остальных библиотеках, начиная с начала командной строки.  
  
> [!NOTE]
>  LINK больше не принимает точку с запятой \(или любые другие символы\) за начало комментария в файлах ответа и упорядоченных файлах.  точки с запятой распознаются как начало комментариев только в файлах определения модуля \(DEF\).  
  
 LINK в качестве исходных данных используется следующие типы файлов.  
  
-   [OBJ\-файлы.](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [файлы .netmodule](../Topic/.netmodule%20Files%20as%20Linker%20Input.md)  
  
-   [LIB\-файлы.](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [EXP\-файлы.](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [DEF\-файлы](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [PDB\-файлы.](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [RES\-файлы.](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [EXE\-файлы.](../Topic/.Exe%20Files%20as%20Linker%20Input.md)  
  
-   [TXT\-файлы.](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [ILK\-файлы.](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)