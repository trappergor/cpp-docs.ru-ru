---
title: Ошибка компилятора C2791 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2791
dev_langs:
- C++
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65a3d399ed6c7f25b849335328550526ecf7a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2791"></a>Ошибка компилятора C2791
Недопустимое использование «super»: «класс» не имеет базовых классов  
  
 Ключевое слово [super](../../cpp/super.md) было использовано в контексте функции-члена класса, который не имеет базовых классов.  
  
 Следующий пример приводит к возникновению ошибки C2791:  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```