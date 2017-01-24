---
title: "Предупреждение компилятора (уровень&#160;3) C4622 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4622"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4622"
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;3) C4622
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

перезапись отладочной информации, сформированной во время создания предкомпилированного заголовка в объектном файле: "файл"  
  
 Информация CodeView в указанном файле была утеряна при выполнении компиляции с параметром [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) \(использование предкомпилированных заголовков\).  
  
 Переименуйте объектный файл \(с использованием параметра [\/Fo](../../build/reference/fo-object-file-name.md)\) при создании или использовании файла предкомпилированного заголовка и выполните компоновку с использованием нового объектного файла.