---
title: "Неустранимая ошибка NMAKE U1056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1056"
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка NMAKE U1056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается найти процессор команд  
  
 Командный процессор не расположен в пути, указанном в переменных окружения **COMSPEC** или **PATH**.  
  
 Для выполнения команд NMAKE использует COMMAND.COM или CMD.EXE в качестве командного процессора.  В начале выполняется поиск командного процессора в пути, заданном в **COMSPEC**.  Если **COMSPEC** не существует, NMAKE выполняет поиск в папках, указанных в **PATH**.