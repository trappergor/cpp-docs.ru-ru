---
title: "Предупреждение компилятора (уровень 4) C4232 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4232"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4232"
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4232
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нестандартное расширение: "идентификатор": адрес dllimport "dllimport" не является статическим, идентичность не гарантируется  
  
 При использовании расширений Майкрософт \(\/Ze\) можно передать нестатическое значение в качестве адреса функции с помощью модификатора **dllimport**.  В режиме ANSI\-совместимости \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) это приводит к возникновению ошибки.  
  
 Следующий пример приводит к возникновению ошибки C4232:  
  
```  
// C4232.c  
// compile with: /W4 /Ze /c  
int __declspec(dllimport) f();  
int (*pfunc)() = &f;   // C4232  
```