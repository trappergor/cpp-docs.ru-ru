---
title: "Ошибка компилятора C2441 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2441"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2441"
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C2441
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": символ, объявленный с параметром \_\_declspec\(process\), должен быть константой в режиме \/clr:pure  
  
 По умолчанию в режиме **\/clr:pure** переменные указываются на весь домен приложения.  Переменные, помеченные как `__declspec(process)`, в режиме **\/clr:pure** могут привести к возникновению ошибок, если их изменить в одном домене приложения и использовать для чтения в другом.  
  
 Поэтому компилятор обеспечивает в режиме **\/clr:pure** принудительное использование переменных для каждого процесса как `const`, что делает их доступными только для чтения во всех доменах приложения.  
  
 Дополнительные сведения см. в разделах [процесс](../../cpp/process.md) и [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Пример  
 В следующем примере возникает ошибка C2441.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```