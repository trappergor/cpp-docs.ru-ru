---
title: "Устранение проблем построения выпуска | Microsoft Docs"
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
  - "отладочные построения, перезаписи памяти"
  - "память, перезаписи"
  - "построения выпуска, устранение неполадок"
  - "выпускные построения - устранение неполадок"
  - "устранение неполадок - Visual C++, построения выпуска"
ms.assetid: a0c0818e-4c47-4fe0-a611-50d61a41bd88
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Устранение проблем построения выпуска
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если код создает ошибки компилятора после перехода от отладочного построения к построению выпуска, следует проверить следующие моменты.  
  
 Во время оптимизированного построения \(построения выпуска\) могут появиться предупреждения компилятора, которые не отображались при отладочном построении.  
  
-   [Проверьте операторы ASSERT](../../build/reference/using-verify-instead-of-assert.md)  
  
-   [Воспользуйтесь отладочным построением для проверки перезаписи памяти](../Topic/Using%20the%20Debug%20Build%20to%20Check%20for%20Memory%20Overwrite.md)  
  
-   [Включите создание сведений об отладке для построения выпуска](../../build/reference/how-to-debug-a-release-build.md)  
  
-   [Проверьте перезапись памяти](../../build/reference/checking-for-memory-overwrites.md)  
  
## См. также  
 [Построения выпуска](../../build/reference/release-builds.md)   
 [Распространенные проблемы, возникающие при создании построений выпуска](../../build/reference/common-problems-when-creating-a-release-build.md)   
 [Оптимизация кода](../../build/reference/optimizing-your-code.md)