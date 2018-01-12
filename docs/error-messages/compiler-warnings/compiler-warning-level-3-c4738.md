---
title: "Предупреждение (уровень 3) C4738 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4738
dev_langs: C++
helpviewer_keywords: C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 30f56b7963d8c6e98d4564ec90adee6bd3d29f9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4738"></a>Предупреждение компилятора (уровень 3) C4738
хранение результатов в памяти в 32-разрядном формате с плавающей запятой, возможно снижение производительности  
  
 C4738 предупреждает о том, что результат присваивания, приведения, передачи аргумента или другой операции может потребоваться округлить, или, что операция не хватило регистров и требуется для использования памяти. Это может привести к потере производительности.  
  
 Чтобы устранить это предупреждение и избежать округления, компиляция с [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md) или использовать `double` вместо `float`.  
  
 Чтобы устранить это предупреждение и предотвращения нехватки регистров, изменить порядок вычисления и изменить применение встраивание  
  
 Это предупреждение отключено по умолчанию. Дополнительные сведения см. в разделе [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4738:  
  
```  
// C4738.cpp  
// compile with: /c /fp:precise /O2 /W3  
// processor: x86  
#include <stdio.h>  
  
#pragma warning(default : 4738)  
  
float func(float f)  
{  
    return f;  
}  
  
int main()  
{  
    extern float f, f1, f2;  
    double d = 0.0;  
  
    f1 = func(d);  
    f2 = (float) d;  
    f = f1 + f2;   // C4738  
    printf_s("%f\n", f);  
}  
```