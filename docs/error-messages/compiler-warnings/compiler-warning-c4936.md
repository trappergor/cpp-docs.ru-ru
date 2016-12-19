---
title: "Предупреждение компилятора C4936 | Microsoft Docs"
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
  - "C4936"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4936"
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора C4936
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Данный \_\_declspec поддерживается только при компиляции с параметрами \/clr или \/clr:pure  
  
 Использовался модификатор `__declspec`, но модификатор `__declspec` допустим только при компиляции с одним из параметров [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Дополнительные сведения см. в разделах [appdomain](../Topic/appdomain.md) и [process](../../cpp/process.md).  
  
 C4936 всегда выдается как ошибка.  Вы можете отключить C4936 с помощью директивы [warning](../../preprocessor/warning.md).  
  
 При компиляции следующего примера возникнет ошибка C4936:  
  
```  
// C4936.cpp // compile with: /c // #pragma warning (disable : 4936) __declspec(process) int i;   // C4936 __declspec(appdomain) int j;   // C4936  
```