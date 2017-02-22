---
title: "Константы поля st_mode структуры _stat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "S_IFCHR"
  - "S_IFDIR"
  - "_S_IWRITE"
  - "S_IFMT"
  - "_S_IFDIR"
  - "_S_IREAD"
  - "S_IEXEC"
  - "_S_IEXEC"
  - "_S_IFMT"
  - "S_IWRITE"
  - "S_IFREG"
  - "S_IREAD"
  - "_S_IFCHR"
  - "_S_IFREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_S_IEXEC - константа"
  - "_S_IFCHR - константа"
  - "_S_IFDIR - константа"
  - "_S_IFMT - константа"
  - "_S_IFREG - константа"
  - "_S_IREAD - константа"
  - "_S_IWRITE - константа"
  - "S_IEXEC - константа"
  - "S_IFCHR - константа"
  - "S_IFDIR - константа"
  - "S_IFMT - константа"
  - "S_IFREG - константа"
  - "S_IREAD - константа"
  - "S_IWRITE - константа"
  - "st_mode - поля константы"
  - "stat - структура"
  - "stat - структура, константы"
ms.assetid: fd462004-7563-4766-8443-30b0a86174b6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Константы поля st_mode структуры _stat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <sys/stat.h>  
  
```  
  
## Заметки  
 Эти константы используются для указания типа файла в поле **st\_mode** структуры [\_stat](../c-runtime-library/standard-types.md).  
  
 Константы битовой маски описаны ниже:  
  
|Константа|Значение|  
|---------------|--------------|  
|`_S_IFMT`|Маска типа файла|  
|`_S_IFDIR`|Каталог|  
|`_S_IFCHR`|Специальный символ \(указывает устройство, если установлена\)|  
|`_S_IFREG`|Регулярное|  
|`_S_IREAD`|Разрешение на чтение, владелец|  
|`_S_IWRITE`|Разрешение на запись, владелец|  
|`_S_IEXEC`|Разрешение на выполнение\/поиск, владелец|  
  
## См. также  
 [Функции \_stat, \_wstat](../c-runtime-library/reference/stat-functions.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [Стандартные типы](../c-runtime-library/standard-types.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)