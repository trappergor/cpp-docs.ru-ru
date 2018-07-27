---
title: Предупреждение средств компоновщика LNK4217 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4217
dev_langs:
- C++
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 625f3a1b8a67f198b1cb4ca37bd1350229ec20db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300580"
---
# <a name="linker-tools-warning-lnk4217"></a>Предупреждение средств компоновщика LNK4217
локально определенный символ «символ» импортируется в функции «функция»  
  
 [__declspec(dllimport)](../../cpp/dllexport-dllimport.md) был указан для символа, даже если этот символ определен локально. Удалить `__declspec` модификатор, чтобы устранить это предупреждение.  
  
 `symbol` представляет имя символа, который определен в образе. `function` — функция, которая импортирует символ.  
  
 Это предупреждение не будет выводиться при компиляции с помощью параметра [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 LNK4217 также может возникать при попытке связать два модуля вместе, когда следует компилировать второй модуль с библиотекой импорта первого модуля.  
  
```  
// LNK4217.cpp  
// compile with: /LD  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 Затем:  
  
```  
// LNK4217b.cpp  
// compile with: /c  
#include "windows.h"  
__declspec(dllexport) void func(unsigned short*) {}  
```  
  
 При попытке связать эти два модуля приведет LNK4217, компиляция второй пример с библиотекой импорта первого примера, чтобы разрешить.