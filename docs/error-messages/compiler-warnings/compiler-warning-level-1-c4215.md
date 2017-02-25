---
title: "Предупреждение компилятора (уровень 1) C4215 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4215"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4215"
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4215
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нестандартное расширение: long float  
  
 Расширения Майкрософт по умолчанию \(\/Ze\) обрабатывают **long float** как **double**.  В режиме совместимости с ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) это не происходит.  Чтобы сохранить совместимость, следует использовать **double**.  
  
 Следующий пример приводит к возникновению ошибки C4215:  
  
```  
// C4215.cpp  
// compile with: /W1 /LD  
long float a;   // C4215  
  
// use the line below to resolve the warning  
// double a;  
```