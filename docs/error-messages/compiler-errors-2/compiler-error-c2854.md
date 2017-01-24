---
title: "Ошибка компилятора C2854 | Microsoft Docs"
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
  - "C2854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2854"
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

синтаксическая ошибка в прагма\-директиве \#pragma hdrstop  
  
 В прагма\-директиве `#pragma hdrstop` указано недопустимое имя файла.  После прагмы может следовать необязательное имя файла в скобках и кавычках.  
  
 Следующий пример приводит к возникновению ошибки C2854:  
  
```  
// C2854.cpp  
// compile with: /c  
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854  
// try the following line instead  
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )  
```