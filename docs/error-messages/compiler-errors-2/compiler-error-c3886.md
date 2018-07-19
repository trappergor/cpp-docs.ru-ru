---
title: Ошибка компилятора C3886 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3886
dev_langs:
- C++
helpviewer_keywords:
- C3886
ms.assetid: 485f6c12-cc1b-4146-9034-409a0a5e615e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e17e56ac999680728f14d0ea3a98cc7c05b66e31
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268381"
---
# <a name="compiler-error-c3886"></a>Ошибка компилятора C3886
«переменная»: член данных литерала должен быть инициализирован  
  
 Объект [литерала](../../windows/literal-cpp-component-extensions.md) переменная должна быть инициализирована при ее объявлении.  
  
 Следующий пример приводит к возникновению ошибки C3886:  
  
```  
// C3886.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal int staticConst;   // C3886  
   literal int staticConst2 = 0;   // OK  
};  
```