---
title: "Ошибка компилятора C2223 | Microsoft Docs"
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
  - "C2223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2223"
ms.assetid: e4506f0f-0317-4a96-8a90-877a156d7939
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слева от «\-\>идентификатор» должен указывать на структуре или подключить  
  
 Операнд слева от `->` не является указателем класса, структуры или объединения.  
  
 Причиной этой ошибки может быть левый операнд, являющийся не определенной переменной \(следовательно, имеющий тип\) `int`\).