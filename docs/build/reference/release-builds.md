---
title: "Построения выпуска | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "отладочные построения, переключение в выпускное построение"
  - "отладка [C++], построения выпуска"
  - "построения выпуска"
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Построения выпуска
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Построение выпуска использует оптимизации.  При использовании оптимизаций для создания построения выпуска компилятор не создает символьной информации для отладки.  Отсутствие символьной информации для отладки, а также факт, что код не создается для вызовов TRACE и ASSERT, означает, что размер исполняемого файла уменьшается, а скорость выполнения увеличивается.  
  
 В этом разделе приведены сведения о способах и случаях изменения отладочной версии построения на построение выпуска.  В нем также рассматриваются некоторые проблемы, которые могут возникнуть при изменении отладочной версии построения на построение выпуска.  
  
-   [Создание построения выпуска](../../build/reference/how-to-create-a-release-build.md)  
  
-   [Распространенные проблемы, возникающие при создании построений выпуска](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [Устранение проблем возникающих с построениями выпуска](../../build/reference/fixing-release-build-problems.md)  
  
    -   [Изучение операторов ASSERT](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [Использование отладочного построения для проверки затирания памяти](../Topic/Using%20the%20Debug%20Build%20to%20Check%20for%20Memory%20Overwrite.md)  
  
    -   [Отладка построения выпуска](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [Проверка затирания памяти](../../build/reference/checking-for-memory-overwrites.md)  
  
## См. также  
 [Построение проектов C\+\+ в Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)   
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)