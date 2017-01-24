---
title: "Константы файлов | Microsoft Docs"
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
  - "_O_EXCL"
  - "_O_RDWR"
  - "_O_APPEND"
  - "_O_RDONLY"
  - "_O_TRUNC"
  - "_O_CREAT"
  - "_O_WRONLY"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_APPEND - константа"
  - "_O_CREAT - константа"
  - "_O_EXCL - константа"
  - "_O_RDONLY - константа"
  - "_O_RDWR - константа"
  - "_O_TRUNC - константа"
  - "_O_WRONLY - константа"
  - "O_APPEND - константа"
  - "O_CREAT - константа"
  - "O_EXCL - константа"
  - "O_RDONLY - константа"
  - "O_RDWR - константа"
  - "O_TRUNC - константа"
  - "O_WRONLY - константа"
ms.assetid: c8fa5548-9ac2-4217-801d-eb45e86f2fa4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <fcntl.h>  
  
```  
  
## Заметки  
 Целочисленное выражение, сформированное из одной или нескольких констант, определяет тип разрешенных операций чтения или записи.  Оно формируется путем объединения одной или нескольких константы с константой режима преобразования.  
  
 Константы файла выглядят следующим образом:  
  
 `_O_APPEND`  
 Перемещает указатель файла в конец файла перед каждой операцией записи.  
  
 `_O_CREAT`  
 Создает и открывает новый файл для записи; ничего не происходит, если файл с указанным *filename* существует.  
  
 `_O_EXCL`  
 Возвращает значение ошибки, если файл, указанный *filename* существует.  Область применения: только при использовании с `_O_CREAT`.  
  
 `_O_RDONLY`  
 Файл будет открыт только для чтения; если указан этот флаг ни `_O_RDWR`, ни `_O_WRONLY` нельзя использовать.  
  
 `_O_RDWR`  
 Файл будет открыт как для чтения, так и для записи; если указан этот флаг ни `_O_RDONLY`, ни `_O_WRONLY` нельзя использовать.  
  
 `_O_TRUNC`  
 Будет открыт и усечен до нулевой длины существующий файл; файл должен иметь разрешение на запись.  Содержимое файла уничтожается.  Если задан этот флаг, нельзя использовать `_O_RDONLY`.  
  
 `_O_WRONLY`  
 Файл будет открыт только для записи; если указан этот флаг ни `_O_RDONLY`, ни `_O_RDWR` нельзя использовать.  
  
## См. также  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)