---
title: "ALIAS (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Alias"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ALIAS directive"
ms.assetid: d9725c49-58de-41da-ab01-b06a56cf5cf2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ALIAS (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Псевдоним** директива создает другое имя функции.  Это позволяет создать несколько имен для функции или создает библиотеки, позволяющие компоновщик \(LINK.exe\) для сопоставления старая функции к новой функции.  
  
## Синтаксис  
  
```  
  
ALIAS  <  
alias  
> = <  
actual-name  
>  
  
```  
  
#### Параметры  
 `actual-name`  
 Фактическое имя функции или процедуры.  Угловые скобки требуются.  
  
 `alias`  
 Имя избыточности или псевдонима.  Угловые скобки требуются.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)