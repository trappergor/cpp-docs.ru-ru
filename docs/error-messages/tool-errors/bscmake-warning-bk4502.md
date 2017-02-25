---
title: "Предупреждение BSCMAKE BK4502 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK4502"
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
  - "BK4502"
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение BSCMAKE BK4502
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

сокращенный SBR\-файл 'filename' отсутствует в имени файла  
  
 Во время обновления указан SBR\-файл нулевой длины, который не был изначально частью BSC\-файла.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Задано неверное имя файла.  
  
2.  Файл удален. \(Результаты ошибки [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) \).  
  
3.  Файл поврежден, BSCMAKE необходимо выполнить полное построение.