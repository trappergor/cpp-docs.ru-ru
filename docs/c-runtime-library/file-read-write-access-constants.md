---
title: "Константы доступа чтения и записи файлов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.constants.file"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "константы доступа с правом чтения и записи файла"
  - "константы [C++], атрибуты файла"
  - "константы доступа с правом чтения и записи файла"
  - "константы доступа с правом чтения и записи"
  - "константы доступа с правом записи"
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Константы доступа чтения и записи файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <stdio.h>  
```  
  
## Заметки  
 Эти константы определяют тип доступа \(«a», «r» или «w»\), запрошенный для файла.  И [translation mode](../c-runtime-library/file-translation-constants.md) \(«b» или «t»\), и [commit\-to\-disk mode](../Topic/Commit-To-Disk%20Constants.md) \(«с» или «n»\) можно указать с типом доступа.  
  
 Типы доступа описаны ниже.  
  
 **"a"**.  
 Открывает для записи в конец файла \(добавление\); сначала создает файл, если он не существует.  Все операции записи выполняются в конце файла.  Хотя указатель файла может быть перемещен с помощью `fseek` или **rewind**, он всегда возвращается в конец файла перед выполнением любой операции записи.  
  
 **"a\+"**  
 То же, что и выше, но также поддерживает чтение.  
  
 **"r"**  
 Открывает для чтения.  Если файл не существует или не найден, вызов открытия файла завершится ошибкой.  
  
 **"r\+"**  
 Открывает для чтения и записи.  Если файл не существует или не найден, вызов открытия файла завершится ошибкой.  
  
 **"w"**  
 Открывает пустой файл для записи.  Если указанный файл существует, его содержимое удаляется.  
  
 **"w\+"**  
 Открывает пустой файл для чтения и записи.  Если указанный файл существует, его содержимое удаляется.  
  
 Если задан тип доступа "r\+", "w\+" или "a\+", чтение и запись разрешены \(считается, что файл открыт для "обновления"\).  Однако при переключении между чтением и записью должны быть промежуточные операции `fflush`, `fsetpos`, `fseek` или **rewind**.  Для операции `fsetpos` или `fseek` можно задать текущее положение.  
  
## См. также  
 [\_fdopen, \_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)