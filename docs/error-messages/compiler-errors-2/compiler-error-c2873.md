---
title: "Ошибка компилятора C2873 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2873"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2873"
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2873
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": использование символа в объявлении использования не допускается  
  
 В директиве `using` отсутствует ключевое слово [namespace](../Topic/namespace%20Declaration.md).  В связи с этим при компиляции код интерпретируется как [объявление using](../../cpp/using-declaration.md), а не [директива using](../../misc/using-directive-cpp.md).