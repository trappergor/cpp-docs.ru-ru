---
title: "Ошибки положения файлов | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "указатели файлов [C++], ошибки положения файлов"
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ошибки положения файлов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.9.9.1, 4.9.9.4** Значение, задаваемое макросу `errno` функцией `fgetpos` или `ftell` при ошибке  
  
 В случае сбоя функции `fgetpos` или `ftell` для макроса `errno` задается значение константы `EINVAL` из манифеста, если недопустима позиция, или значение EBADF, если недопустим номер файла.  Эти константы определены в файле ERRNO.H.  
  
## См. также  
 [Функции библиотеки](../c-language/library-functions.md)