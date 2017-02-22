---
title: "Повторное использование подставляемого файла | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "встроенные файлы, повторное использование (NMAKE)"
  - "программа NMAKE, встроенные файлы"
  - "повторное использование встроенного файла"
ms.assetid: d42dbffb-2cef-4ccb-9a1f-20b8ef81481c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Повторное использование подставляемого файла
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для повторного использования встроенный файл укажите \<\<*имя файла*, в котором определен и файл сначала используется, то *имя файла* без \<\< повторного использования далее в этих же или другой команды.  Команда по созданию подставляемого файла должна выполняться до выполнения всех других команд, использующих этот файл.  
  
## См. также  
 [Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)