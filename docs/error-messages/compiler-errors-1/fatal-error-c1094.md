---
title: Неустранимая ошибка C1094 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1094
dev_langs:
- C++
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e227cbfaf46eb7616ae63eda02816e7d274ab85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227521"
---
# <a name="fatal-error-c1094"></a>Неустранимая ошибка C1094
"-Zmval1": параметр командной строки несовместим со значением, использованным для сборки предкомпилированного заголовка ("-Zmval2")  
  
 Значение, передаваемое [/Yc](../../build/reference/yc-create-precompiled-header-file.md) должно быть то же значение, передаваемое [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm** значения должны быть одинаковыми во всех компиляциях, использующих или создающих же предкомпилированные файл заголовка).  
  
 Следующий пример приводит к возникновению ошибки C1094:  
  
```  
// C1094.h  
int func1();  
```  
  
 Затем:  
  
```  
// C1094.cpp  
// compile with: /Yc"C1094.h" /Zm200  
int u;  
int main() {  
   int sd = 32;  
}  
#include "C1094.h"  
```  
  
 Затем:  
  
```  
// C1094b.cpp  
// compile with: /Yu"C1094.h" /Zm300 /c  
#include "C1094.h"   // C1094 compile with /Zm200  
void Test() {}  
```