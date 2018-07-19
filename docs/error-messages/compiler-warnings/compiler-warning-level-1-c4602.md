---
title: Ошибка компилятора предупреждение (уровень 1) C4602 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4602
dev_langs:
- C++
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2c25fd983f1ac7cebcc568a0b47c06c4d8e23a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279531"
---
# <a name="compiler-warning-level-1-c4602"></a>Предупреждение компилятора (уровень 1) C4602
\#Директива #pragma pop_macro: «имя макроса» ранее не #pragma push_macro для этого идентификатора  
  
 Если вы используете [pop_macro](../../preprocessor/pop-macro.md) для конкретного макроса, то должны сначала передать имя макроса в [push_macro](../../preprocessor/push-macro.md). Например, в следующем примере возникает ошибка C4602:  
  
```  
// C4602.cpp  
// compile with: /W1  
int main()  
{  
   #pragma pop_macro("x")   // C4602 x is not on the stack  
}  
```