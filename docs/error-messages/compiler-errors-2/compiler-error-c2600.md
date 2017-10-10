---
title: "Ошибка компилятора C2600 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2600
dev_langs:
- C++
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1fe5383e17212b21c11394c6b987e92aacbe637e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2600"></a>Ошибка компилятора C2600
'функция' : невозможно определить особую функцию-член, созданную компилятором (сначала требуется объявить ее в классе)  
  
 Перед определением функций-членов, таких как конструкторы или деструкторы, для класса они должны быть объявлены в этом классе. Компилятор может создать конструкторы и деструкторы по умолчанию (особые функции-члены), если они не объявлены в классе. Если же определить одну из этих функций без соответствующего объявления в классе, то компилятор обнаружит конфликт.  
  
 Чтобы устранить эту ошибку нужно в объявлении класса объявить каждую функцию-член, которая определена вне объявления класса.  
  
 Следующий пример приводит к возникновению ошибки C2600:  
  
```  
// C2600.cpp  
// compile with: /c  
class C {};  
C::~C() {}   // C2600  
  
class D {  
   D::~D();  
};  
  
D::~D() {}  
```
