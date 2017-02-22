---
title: "Параметры /O (оптимизация кода) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.Optimization"
  - "/o"
  - "VC.Project.VCCLWCECompilerTool.Optimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe - компилятор, производительность"
  - "производительность, компилятор cle.exe"
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Параметры /O (оптимизация кода)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметры **\/O** обеспечивают управление различными способами оптимизации, предназначенными для создания кода максимальной производительности или минимального размера.  
  
-   [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) — оптимизация для получения минимального размера кода.  
  
-   [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) — оптимизация кода для получения максимальной скорости его выполнения.  
  
-   [\/Ob](../../build/reference/ob-inline-function-expansion.md) — контроль над расширением встроенных функций.  
  
-   [\/Od](../../build/reference/od-disable-debug.md) — отключение оптимизации для ускорения компиляции и упрощения отладки.  
  
-   [\/Og](../../build/reference/og-global-optimizations.md) — включение глобальной оптимизации.  
  
-   [\/Oi](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md) — создание встроенных функций для соответствующих вызовов функций.  
  
-   [\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) — задание для компилятора приоритетности оптимизации для уменьшения размера кода над оптимизацией для увеличения скорости его выполнения.  
  
-   [\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) \(настройка по умолчанию\) — задание для компилятора приоритетности оптимизации для уменьшения размера кода над оптимизацией для увеличения скорости его выполнения.  
  
-   [\/Ox](../../build/reference/ox-full-optimization.md) — выбор полной оптимизации.  
  
-   [\/Oy](../../build/reference/oy-frame-pointer-omission.md) — отключение создания указателей фреймов для стека вызовов, что позволяет повысить скорость вызова функций.  
  
## Примечания  
 Также можно объединить несколько параметров **\/O** в один оператор option.  Например, `/Odi` — то же самое, что `/Od /Oi`.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)