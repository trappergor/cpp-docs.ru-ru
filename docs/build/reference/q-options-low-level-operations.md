---
title: "Параметры /Q (низкоуровневые операции) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/q"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Q - параметр компилятора [C++]"
  - "-Q - параметр компилятора [C++]"
  - "/Q - параметр компилятора [C++]"
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# Параметры /Q (низкоуровневые операции)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Можно использовать параметры компилятора **\/Q** выполнить следующие операции низкоуровневые компилятора:  
  
-   [\/Qfast\_transcendentals \(принудительное использование быстрых трансцендентных функций\)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): создает быстрые трансцендентные функции.  
  
-   [\/QIfist \(Suppress \_ftol\)](../../build/reference/qifist-suppress-ftol.md): подавляет использование функции `_ftol` при необходимости преобразования из типа с плавающей запятой к целому типу \(только архитектура x86\).  
  
-   [\/Qimprecise\_fwaits \(Удалить ожидания в блоке try\)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): удаляет команды `fwait` в блоках `try`.  
  
-   [\/Qpar \(автоматический параллелизатор\)](../Topic/-Qpar%20\(Auto-Parallelizer\).md): Включает автоматическую параллелизацию циклов, которые помечены с помощью директивы [цикл \#pragma \(\)](../../preprocessor/loop.md).  
  
-   [\/Qpar\-report \(уровень отчетности автоматического параллелизатора\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): Включает уровни отчета для автоматической параллелизации.  
  
-   [\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md): Подавляет оптимизацию для чисел с плавающей запятой с регистр и для перемещений между памятью и регистрами MMX.  
  
-   [\/Qvec\-report \(уровень отчетности автоматического векторизатора\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): Включает уровни отчетов для автоматического vectorization.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)