---
title: "Зарезервированные слова | Microsoft Docs"
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
  - "code"
  - "CONFORMING"
  - "DISCARDABLE"
  - "Description"
  - "base"
  - "APPLOADER"
  - "Data"
  - "DYNAMIC"
  - "DEV386"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEF-файлы [C++], зарезервированные слова"
  - "DEF-файлы [C++], зарезервированные слова"
  - "компоновщик [C++], зарезервированные слова"
  - "зарезервированные слова [C++]"
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Зарезервированные слова
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ниже приведен список зарезервированных слов компоновщика.  При использовании этих имен в качестве аргументов в [операторах определения модуля](../Topic/Module-Definition%20\(.Def\)%20Files.md) их необходимо заключать в двойные кавычки \(""""\).  
  
||||  
|-|-|-|  
|**APPLOADER**1|**INITINSTANCE**2|**PRELOAD**|  
|**BASE**|**IOPL**|**PRIVATE**|  
|**CODE**|**LIBRARY**1|**PROTMODE**2|  
|**CONFORMING**|**LOADONCALL**1|**PURE**1|  
|**DATA**|**LONGNAMES**2|**READONLY**|  
|**DESCRIPTION**|`MOVABLE`1|**READWRITE**|  
|**DEV386**|**MOVEABLE**1|**REALMODE**1|  
|**DISCARDABLE**|**MULTIPLE**|**RESIDENT**|  
|**DYNAMIC**|**ИМЯ**|**RESIDENTNAME**1|  
|**EXECUTE\-ONLY**|**NEWFILES**2|**SECTIONS**|  
|**EXECUTEONLY**|`NODATA`1|**SEGMENTS**|  
|**EXECUTEREAD**|**NOIOPL**1|**SHARED**|  
|**EXETYPE**|**NONAME**|**SINGLE**|  
|**EXPORTS**|**NONCONFORMING**1|**STACKSIZE**|  
|**FIXED**1|**NONDISCARDABLE**|**STUB**|  
|**FUNCTIONS**2|**НЕТ**|**VERSION**|  
|**HEAPSIZE**|**NONSHARED**|**WINDOWAPI**|  
|**IMPORTS**|**NOTWINDOWCOMPAT**1|**WINDOWCOMPAT**|  
|**IMPURE**1|**OBJECTS**|**WINDOWS**|  
|**INCLUDE**2|**OLD**1||  
  
 1. Когда компоновщик встречает этот термин, он выдает предупреждение \("пропускается"\).  Тем не менее, слово по\-прежнему остается зарезервированным.  
  
 2. Компоновщик пропускает это слово, но не выдает предупреждение.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)