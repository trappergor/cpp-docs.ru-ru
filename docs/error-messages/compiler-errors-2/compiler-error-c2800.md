---
title: Ошибка компилятора C2800 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2800
dev_langs:
- C++
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9dd9723513042ae7ef6d63914f5abecd63192e37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235601"
---
# <a name="compiler-error-c2800"></a>Ошибка компилятора C2800
«оператор» не может быть перегружен  
  
 Следующие операторы не могут быть перегружены: доступ к члену класса (`.`), указатель на член (`.*`), разрешение области действия (`::`), условное выражение (`? :`), и `sizeof`.  
  
 Следующий пример приводит к возникновению ошибки C2800:  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```