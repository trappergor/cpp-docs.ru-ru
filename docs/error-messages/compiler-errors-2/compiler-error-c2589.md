---
title: Ошибка компилятора C2589 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c15589358979f554a9c17114f7d78b05dd83c472
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2589"></a>Ошибка компилятора C2589
«Идентификатор»: недопустимый маркер справа от "::"  
  
 Если класса, структуры или объединения имя отображается слева от оператора разрешения области действия (двойное двоеточие), маркер справа необходимо класса, структуры или члена объединения. В противном случае любой глобальный идентификатор может появиться справа.  
  
 Оператор разрешения области действия не могут быть перегружены.  
  
 Следующий пример приводит к возникновению ошибки C2589:  
  
```  
// C2589.cpp  
void Test(){}  
class A {};  
void operator :: ();   // C2589  
  
int main() {  
   ::Test();  
}  
```