---
title: Ошибка компилятора C3609 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3609
dev_langs:
- C++
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b0f3ec99e5d528967fb7b02bc9d198402b16e18
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33258300"
---
# <a name="compiler-error-c3609"></a>Ошибка компилятора C3609
member: запечатанная или окончательная функция должна быть виртуальной  
  
 [Запечатанный](../../windows/sealed-cpp-component-extensions.md) и [окончательного](../../cpp/final-specifier.md) ключевые слова допустимы только для класса, структуры или члена функции, помеченной `virtual`.  
  
 Следующий пример приводит к возникновению ошибки C3609:  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
