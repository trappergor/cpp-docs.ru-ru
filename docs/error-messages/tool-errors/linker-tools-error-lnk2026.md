---
title: "Ошибка средств компоновщика LNK2026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2026"
ms.assetid: 9955bf7c-59b5-4fa1-8481-147db0d7df45
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка средств компоновщика LNK2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

небезопасный модуль для образа SAFESEH  
  
 Был указан параметр [\/SAFESEH](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md), но модуль несовместим с функцией безопасной обработки исключений.  Если требуется использовать этот модуль с параметром **\/SAFESEH**, необходимо выполнить повторную компиляцию модуля компилятором Visual C\+\+ .NET 2003 \(или последующих версий\).