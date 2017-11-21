---
title: "Ошибка компилятора C2134 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2134
dev_langs: C++
ms.assetid: d45cb3e8-0be4-4bd6-8be9-5f8d2384363f
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 380a26192b907100f3257b4ca9ee66395f18c2c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2134"></a>Ошибка компилятора C2134
«функция»: вызов не связан в константном выражении  
  
 Функция, объявленная как constexpr может вызывать только другие функции, объявленные как constexpr.  
  
 Следующий пример приводит к возникновению ошибки C2134:  
  
```  
// C2134.cpp  
// compile with: /c  
int A() {  
    return 42;  
};  
  
constexpr int B() {  
    return A();  // Error C2134: 'A': call does not result in a constant expression.  
}  
```  
  
 Возможное решение:  
  
```  
// C2134b.cpp  
constexpr int A() {  // add constexpr to A, since it meets the requirements of constexpr.  
    return 42;  
};  
  
constexpr int B() {  
    return A();  // No error  
}  
```