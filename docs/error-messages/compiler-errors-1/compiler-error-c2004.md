---
title: Ошибка компилятора C2004 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4030ea3c82c1a893ebf35903d3fbc362c594282
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164742"
---
# <a name="compiler-error-c2004"></a>Ошибка компилятора C2004
требуется "defined(id)"  
  
 Идентификатор должен быть заключен в круглые скобки после ключевого слова препроцессора.  
  
 Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: отсутствуют круглые скобки в директиве препроцессора. Если в директиве препроцессора отсутствует закрывающая круглая скобка, компилятор выдаст сообщение об ошибке.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2004:  
  
```  
// C2004.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG   // C2004  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```  
  
## <a name="example"></a>Пример  
 Возможное решение  
  
```  
// C2004b.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG)  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```