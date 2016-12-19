---
title: "Ошибка средств компоновщика LNK1200 | Microsoft Docs"
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
  - "LNK1200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1200"
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка средств компоновщика LNK1200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ошибка при чтении базы данных "имя файла" программы  
  
 Не удается прочитать базу данных программы.  
  
 Данная ошибка может быть вызвана повреждением файла.  
  
 Если `filename` является базой данных программы для объектного файла, следует выполнить повторную компиляцию объектного файла с параметром [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).  
  
 Если `filename` является базой данных программы для основного файла вывода, и данная ошибка возникает во время инкрементной компоновки, следует удалить базу данных программы и повторно выполнить компоновку.