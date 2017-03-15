---
title: "Порядок параметров CL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe - компилятор, установка параметров"
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Порядок параметров CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметры могут находиться в любом месте командной строки CL, за исключением параметра \/link, который должен стоять последним.  Компилятор начинает обработку с параметров, заданных в [переменной среды CL](../../build/reference/cl-environment-variables.md), а затем читает командную строку слева направо, обрабатывая командные файлы в том порядке, в котором они встречаются.  Каждый параметр применяется ко всем файлам, указанным в командной строке.  Если программа CL встречает несовместимые параметры, используется параметр, стоящий правее всех.  
  
## См. также  
 [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)