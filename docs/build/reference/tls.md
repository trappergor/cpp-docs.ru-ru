---
title: "/TLS | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/TLS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/TLS - параметр программы dumpbin"
  - "-TLS - параметр программы dumpbin"
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /TLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выводит структуру IMAGE\_TLS\_DIRECTORY исполняемого файла.  
  
## Заметки  
 При указании параметра \/TLS выводятся поля структуры TLS и адреса функций обратного вызова TLS.  
  
 Если программа не использует локальную память потоков, ее образ не будет содержать структуру TLS.  Дополнительные сведения см. в разделе [поток](../../cpp/thread.md).  
  
 Структура IMAGE\_TLS\_DIRECTORY определена в winnt.h.  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)