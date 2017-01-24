---
title: "/LOADCONFIG | Microsoft Docs"
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
  - "/loadconfig"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LOADCONFIG - параметр программы dumpbin"
  - "LOADCONFIG - параметр (программа dumpbin)"
  - "-LOADCONFIG - параметр (программа dumpbin)"
ms.assetid: 24667afe-9bee-4f6e-ae72-f534c0050428
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LOADCONFIG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LOADCONFIG  
```  
  
## Заметки  
 Этот параметр вызывает создание дампа структуры IMAGE\_LOAD\_CONFIG\_DIRECTORY — это необязательная структура, используемая загрузчиком Windows NT и определенная в файле WINNT.H.  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)