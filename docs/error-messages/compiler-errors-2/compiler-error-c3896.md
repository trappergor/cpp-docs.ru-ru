---
title: "Ошибка компилятора C3896 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3896
dev_langs: C++
helpviewer_keywords: C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4aa98283d3c83f64ba461bf818a88599f97434e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3896"></a>Ошибка компилятора C3896
«член»: недопустимый инициализатор: этот член данных литерала можно инициализировать только с «nullptr»  
  
 Объект [литерала](../../windows/literal-cpp-component-extensions.md) член данных инициализирован неправильно.  В разделе [nullptr](../../windows/nullptr-cpp-component-extensions.md) для получения дополнительной информации.  
  
 Следующий пример приводит к возникновению ошибки C3896:  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```