---
title: "Пустой и неопределенный макрос | Microsoft Docs"
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
helpviewer_keywords: 
  - "макросы, пустой и неопределенный"
  - "программа NMAKE, пустой макрос"
  - "программа NMAKE, неопределенный макрос"
  - "Пустой макрос (NMAKE)"
  - "неопределенный макрос и NMAKE"
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Пустой и неопределенный макрос
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Пустой и неопределенный макросы разворачиваются в пустые строки, но макрос, определенный как пустая строка, рассматривается как определенный в выражениях препроцессора.  Чтобы определить макрос как пустую строку, не указывайте никаких знаков, кроме знаков пробела или табуляции посла знака равенства \(\=\) в командной строке или командном файле, и заключите пустую строку или определение в двойные кавычки \(" "\).  Чтобы отменить определение макроса, используйте **\!UNDEF.** Дополнительные сведения см. в разделе [Директивы обработки файлов makefile](../build/makefile-preprocessing-directives.md).  
  
## См. также  
 [Определение макроса NMAKE](../build/defining-an-nmake-macro.md)