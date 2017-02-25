---
title: "VCPROFILE_PATH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VCPROFILE_PATH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_PATH - переменная среды"
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# VCPROFILE_PATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает каталог, в котором создаются PGC\-файлы.  
  
## Синтаксис  
  
```  
VCPROFILE_PATH=path  
```  
  
#### Параметры  
 `path`  
 Каталог, в который будут добавляться PGC\-файлы.  
  
## Заметки  
 По умолчанию PGC\-файлы создаются в том же каталоге, в котором располагается профилируемый двоичный файл.  Тем не менее, если абсолютного пути у двоичного файла нет, что может происходить, когда сценарии профилировки двоичного файла выполняются на машине, отличной от той, на которой производилось его построение, то существующий путь можно указать, задав его с помощью параметра `VCPROFILE_PATH`.  
  
## Пример  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## См. также  
 [Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)