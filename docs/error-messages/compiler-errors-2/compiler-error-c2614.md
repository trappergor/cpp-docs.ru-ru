---
title: Ошибка компилятора C2614 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2614
dev_langs:
- C++
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5783abd96e356affb8537f6fec278e368c692a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229781"
---
# <a name="compiler-error-c2614"></a>Ошибка компилятора C2614
«класс1»: недопустимая инициализация члена: «класс2» не является базовым классом или членом  
  
 Только члены или базовые классы могут отображаться в списке инициализации для класса или структуры.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2614.  
  
```  
// C2614.cpp  
// compile with: /c  
struct A {  
   int i;  
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A  
};  
  
struct A2 {  
   int B;  
   int i;  
   A2( int ia ) : B( i ) {};   // OK  
};  
```