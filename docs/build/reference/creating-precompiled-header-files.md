---
title: "Создание файлов предкомпилированных заголовков | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PCH-файлы, создание"
  - "cl.exe - компилятор, предварительная компиляция кода"
  - "PCH-файлы, создание"
  - "файлы предкомпилированного заголовка, создание"
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Создание файлов предкомпилированных заголовков
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В компиляторах Microsoft C и C\+\+ предусматриваются параметры для предварительной компиляции любого, в том числе встроенного, кода C или C\+\+.  Это позволяет скомпилировать стабильное тело кода и сохранить скомпилированное состояние кода в файле. При последующей компиляции можно объединять предварительно скомпилированный код с кодом, находящимся на этапе разработки.  В этом случае любые последующие компиляции выполняются быстрее, поскольку не требуется повторная компиляция стабильного кода.  
  
 В этом разделе подробно освещены следующие вопросы, связанные с предкомпилированными заголовками:  
  
-   [Случаи использования предварительной компиляции исходного кода](../../build/reference/when-to-precompile-source-code.md)  
  
-   [Два варианта предварительной компиляции кода](../../build/reference/two-choices-for-precompiling-code.md)  
  
-   [Правила согласованности предкомпилированных заголовков](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [Использование предкомпилированных заголовков в проекте](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 Дополнительные сведения о параметрах компилятора, связанных с предкомпилированными заголовками, см. в разделе [\/Y \(Предкомпилированные заголовки\)](../../build/reference/y-precompiled-headers.md).  
  
## См. также  
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)