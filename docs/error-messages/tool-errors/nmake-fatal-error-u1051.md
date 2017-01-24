---
title: "Неустранимая ошибка NMAKE U1051 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1051"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1051"
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка NMAKE U1051
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недостаточно памяти  
  
 Недостаточно памяти для NMAKE \(в том числе и виртуальной\), поскольку файл makefile слишком большой или сложный.  
  
### Возможные способы устранения данной ошибки  
  
1.  Освободите пространство на диске.  
  
2.  Увеличьте размер файла разбиения по страницам Windows NT или Windows.  
  
3.  Если используется только часть файла makefile, разделите его на несколько файлов меньшего размера или используйте директивы предварительной обработки **\!IF** для ограничения объема обработки с помощью NMAKE.  К директивам **\!IF** относятся **\!IF**, `!IFDEF`, **\!IFNDEF**, **\!ELSE IF**, **\!ELSE** `IFDEF` и **\!ELSE** `IFNDEF`.