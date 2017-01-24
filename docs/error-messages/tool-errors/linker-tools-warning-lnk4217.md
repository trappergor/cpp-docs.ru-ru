---
title: "Предупреждение средств компоновщика LNK4217 | Microsoft Docs"
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
  - "LNK4217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4217"
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение средств компоновщика LNK4217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

локально определенный символ "символ" импортируется в функции "функция"  
  
 Для символа указан модификатор [\_\_declspec\(dllimport\)](../../cpp/dllexport-dllimport.md), в то время как этот символ определен локально.  Для устранения предупреждения удалите модификатор `__declspec`.  
  
 `symbol` — это символьное имя, определенное внутри образа.  `function` это функция, которая импортирует символ.  
  
 Данное предупреждение не будет выводиться при компиляции с использованием параметра [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Предупреждение LNK4217 также может возникнуть при попытке скомпоновать вместе два модуля, в то время как следует компилировать второй модуль с библиотекой импорта первого модуля.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 И далее,  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 При компоновке этих двух модулей возникнет предупреждение LNK4217. Для его устранения скомпилируйте второй модуль с библиотекой импорта первого модуля.