---
title: "Предупреждение компилятора (уровень 2) C4653 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4653"
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 2) C4653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

параметр компилятора "параметр" несовместим с предкомпилированным заголовком; текущий параметр командной строки пропускается  
  
 Параметр, заданный с помощью параметра [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) \(использовать предкомпилированные заголовки\), несовместим с параметрами, заданными во время создания предкомпилированного заголовка.  Данная компиляция использовала параметр, заданный при создании предкомпилированного заголовка.  
  
 Это предупреждение может возникать, если при компиляции предкомпилированного заголовка в параметре [\/Zp](../Topic/-Zp%20\(Struct%20Member%20Alignment\).md) было указано другое значение.