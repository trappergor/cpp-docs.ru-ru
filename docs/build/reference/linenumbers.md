---
title: "/LINENUMBERS | Microsoft Docs"
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
  - "/linenumbers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINENUMBERS - параметр программы dumpbin"
  - "номера строк"
  - "LINENUMBERS - параметр (программа dumpbin)"
  - "-LINENUMBERS - параметр (программа dumpbin)"
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /LINENUMBERS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINENUMBERS  
```  
  
## Заметки  
 Этот параметр отображает номера строк в формате COFF.  Номера строк присутствуют в объектном файле если он был компилирован с помощью Program Database \(\/Zi\), C7 Compatible \(\/Z7\), or Line Numbers Only \(\/Zd\).  Исполняемый файл или DLL\-файл содержит номера строк в формате COFF так, если бы он был связан с Generate Debug Info \(\/DEBUG\).  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)