---
title: "Командная строка DUMPBIN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dumpbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DUMPBIN - программа, командная строка"
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Командная строка DUMPBIN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для запуска DUMPBIN используется следующий синтаксис:  
  
```  
DUMPBIN [options] files...  
```  
  
 Следует указать один или несколько двоичных файлов и параметры, необходимые для управления данными.  DUMPBIN отображает сведения в стандартном выходном потоке.  Можно перенаправить их в файл или использовать параметр \/OUT для указания выходного файла.  
  
 При запуске DUMPBIN без указания параметров, DUMPBIN отображает сведения, доступные при использовании параметра \/SUMMARY.  
  
 При вводе команды `dumpbin` без других параметров командной строки DUMPBIN отображает описание использования программы.  
  
## См. также  
 [Средства построения С\/C\+\+](../Topic/C-C++%20Build%20Tools.md)   
 [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md)