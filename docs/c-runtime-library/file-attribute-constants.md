---
title: "Константы атрибутов файлов | Microsoft Docs"
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
  - "A_HIDDEN"
  - "_A_NORMAL"
  - "_A_SUBDIR"
  - "_A_RDONLY"
  - "A_NORMAL"
  - "A_SUBDIR"
  - "_A_SYSTEM"
  - "c.constants.file"
  - "_A_HIDDEN"
  - "A_RDONLY"
  - "_A_ARCH"
  - "A_ARCH"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_A_ARCH - константа"
  - "_A_HIDDEN - константа"
  - "_A_NORMAL - константа"
  - "_A_RDONLY - константа"
  - "_A_SUBDIR - константа"
  - "_A_SYSTEM - константа"
  - "константы [C++], атрибуты файла"
  - "константы атрибутов файлов [C++]"
  - "файлы [C++], константы атрибутов файлов"
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы атрибутов файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <io.h>  
```  
  
## Заметки  
 Эти константы определяют текущие атрибуты файла или каталога, определенные функцией.  
  
 Атрибуты представлены следующими константами манифеста:  
  
 `_A_ARCH`  
 Архив.  Задается при изменении файла и очищается командой BACKUP.  Значение: 0x20  
  
 `_A_HIDDEN`  
 Скрытый файл.  Обычно не отображается командой DIR, если не используется параметр \/AH.  Возвращает сведения об обычных файлах и файлах с этим атрибутом.  Значение: 0x02  
  
 `_A_NORMAL`  
 Обычный.  Файл можно считывать и в файл можно записывать без ограничений.  Значение: 0x00  
  
 `_A_RDONLY`  
 Только для чтения.  Файл невозможно открыть для записи, и файл с тем же именем невозможно создать.  Значение: 0x01  
  
 `_A_SUBDIR`  
 Подкаталог.  Значение: 0x10  
  
 `_A_SYSTEM`  
 Системный файл.  Обычно не отображается командой DIR, если не используется параметр \/AS.  Значение: 0x04  
  
 Несколько констант могут быть объединены оператором OR \(&#124;\).  
  
## См. также  
 [Функции поиска имени файла](../c-runtime-library/filename-search-functions.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)