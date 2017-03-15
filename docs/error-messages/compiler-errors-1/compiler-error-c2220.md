---
title: "Ошибка компилятора C2220 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2220"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2220"
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Ошибка компилятора C2220
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предупреждение обработано как ошибка, объектный файл не создан  
  
 [\/WX](../../build/reference/compiler-option-warning-level.md) заставляет компилятор обрабатывать все предупреждения как ошибки.  Поскольку возникла ошибка, объект или исполняемый файл не был создан.  
  
 Эта ошибка появляется только при флажок **\/WX** задания и предупреждение возникает во время компиляции.  Чтобы устранить эту ошибку, необходимо удалить все предупреждения в проекте.  
  
### Чтобы устранить, используйте один из следующих методов  
  
-   Исправить проблемы, вызывающие предупреждения в проекте.  
  
-   Компилировать в нижнем предупреждение уровень\- для примере используйте **\/W3** вместо **\/W4**.  
  
-   Используйте директиву pragma [warning](../../preprocessor/warning.md), чтобы отключить или запретить определенное предупреждение.  
  
-   Не используйте **\/WX** компилироваться.