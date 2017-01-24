---
title: "Массивы в выражениях | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], в выражениях"
  - "выражения [C++], массивы в"
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Массивы в выражениях
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если идентификатор типа массива отображается в выражении, отличном от `sizeof`, взятия адреса \(**&**\) или инициализации ссылки, оно преобразуется в указатель на первый элемент массива.  Например:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 Указатель `psz` указывает на первый элемент массива `szError1`.  Обратите внимание, что массивы, в отличие от указателей, не являются изменяемыми l\-значениями.  Таким образом, следующее присвоение незаконно.  
  
```  
szError1 = psz;  
```  
  
## См. также  
 [Массивы](../Topic/Arrays%20\(C++\).md)