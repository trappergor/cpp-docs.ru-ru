---
title: "Предупреждение командной строки D9027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9027"
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение командной строки D9027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

пропуск файл '\<filename\>' источника  
  
 Программа CL.exe пропустила входной исходный файл.  
  
 Причиной этого предупреждения может быть пробел между параметром \/Fo и именем выходного файла в командной строке с параметром \/c.  Примеры.  
  
```  
cl /c /Fo output.obj input.c   
```  
  
 Из\-за пробела между \/Fo и `output.obj,` программа CL.exe примет `output.obj` за имя входного файла.  Чтобы устранить это предупреждение, удалите лишний пробел:  
  
```  
cl /c /Fooutput.obj input.c   
```