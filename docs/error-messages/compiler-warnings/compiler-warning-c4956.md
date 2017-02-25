---
title: "Предупреждение компилятора C4956 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4956"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4956"
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора C4956
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": этот тип недоступен для проверки  
  
 Это предупреждение создается, если указано [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md), но код содержит тип, не подлежащий проверке.  
  
 Для получения дополнительной информации см. [Чистый и проверяемый код](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [\/wd](../../build/reference/compiler-option-warning-level.md).  
  
 В следующем примере возникает ошибка C4956.  
  
```  
// C4956.cpp // compile with: /clr:safe int* p;   // C4956  
```