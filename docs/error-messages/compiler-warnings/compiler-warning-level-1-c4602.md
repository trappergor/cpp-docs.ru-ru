---
title: "Ошибка компилятора предупреждение (уровень 1) C4602 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4602
dev_langs: C++
helpviewer_keywords: C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ff97549aed96263814c4d6a52e7634b6fd8ec04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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