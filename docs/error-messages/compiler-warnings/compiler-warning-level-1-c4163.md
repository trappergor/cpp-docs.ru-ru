---
title: Предупреждение (уровень 1) C4163 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4163
dev_langs:
- C++
helpviewer_keywords:
- C4163
ms.assetid: b08413fd-03fc-4f41-9167-a98976ac12f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d39297a17c5e7c7b6b95fd0e43f33849c092fa1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275545"
---
# <a name="compiler-warning-level-1-c4163"></a>Предупреждение компилятора (уровень 1) C4163
"идентификатор": недоступен в качестве подставляемой функции  
  
 Указанная функция не может использоваться как [встроенная](../../preprocessor/intrinsic.md) функция. Компилятор игнорирует неправильное имя функции.  
  
 Следующий пример приводит к возникновению ошибки C4163.  
  
```  
// C4163.cpp  
// compile with: /W1 /LD  
#include <math.h>  
#pragma intrinsic(mysin)   // C4163  
// try the following line instead  
// #pragma intrinsic(sin)  
```