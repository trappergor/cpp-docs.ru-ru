---
title: "/IMPORTS (DUMPBIN) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/imports"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IMPORTS - параметр программы dumpbin"
  - "IMPORTS - параметр (программа dumpbin)"
  - "-IMPORTS параметр (программа dumpbin)"
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /IMPORTS (DUMPBIN)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IMPORTS[:file]  
```  
  
 Данный параметр отображает список библиотек DLL \(со статистической привязкой и [загруженный с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)\), которые импортируются в исполняемый файл или библиотеку DLL, а также всех отдельных импортированных элементов каждой из данных библиотек DLL.  
  
 Если указать `file` \(необязательно\), это позволит настроить отображение импортированных элементов только для данной библиотеки DLL.  Примеры.  
  
```  
dumpbin /IMPORTS:msvcrt.dll  
```  
  
## Заметки  
 Данный параметр отображает выходные данные, сходные с выходными данными [\/EXPORTS](../../build/reference/dash-exports.md).  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)