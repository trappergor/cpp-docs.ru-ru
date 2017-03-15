---
title: "Предупреждение компилятора (уровень 1) C4652 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4652"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4652"
ms.assetid: 2cf2c666-8cdd-4dd9-bda0-662921498b03
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4652
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

параметр компилятора "параметр" несовместим с предкомпилированным заголовком; текущий параметр командной строки переопределяет параметр, определенный в заголовке  
  
 Указанный параметр командной строки отличается от использованного при создании предкомпилированного заголовка \(PCH\-файла\).  Использован параметр, указанный в командной строке.  
  
 Избежать предупреждения можно путем пересоздания предкомпилированного заголовка с указанным параметром командной строки.