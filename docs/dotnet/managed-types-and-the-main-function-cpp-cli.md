---
title: "Управляемые типы и функция main (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main - функция, в управляемых приложениях"
  - "управляемый код, main() - функция"
ms.assetid: 9d0e9620-58c4-4dac-a0e1-ffeb95f80fa5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Управляемые типы и функция main (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При написании приложения с использованием **\/clr**, аргументы функции **main\(\)** не могут принадлежать к управляемому типу.  
  
 Ниже приведен пример правильной подписи.  
  
```  
// managed_types_and_main.cpp  
// compile with: /clr  
int main(int, char*[], char*[]) {}  
```  
  
## См. также  
 [Управляемые типы](../Topic/Managed%20Types%20\(C++-CLI\).md)