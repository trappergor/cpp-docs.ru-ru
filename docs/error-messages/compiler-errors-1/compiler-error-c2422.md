---
title: "Ошибка компилятора C2422 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 839909b108589655000bfe4a76306c8ee9d7339d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2422"></a>Ошибка компилятора C2422
Недопустимое переопределение сегмента в 'operand'  
  
 Встроенный код ассемблера неправильно использует оператор переопределения сегмента (двоеточие) над операндом.  Возможные причины:  
  
-   Регистр перед оператором не регистрации сегмента.  
  
-   Регистр перед оператором не только регистром сегмента в операнде.  
  
-   Оператор переопределения сегмента появляется внутри оператора косвенного обращения (квадратные скобки).  
  
-   Выражение, следующее за оператор переопределения сегмента не является непосредственным операндом или операндом памяти.  
  
 Следующий пример приводит к возникновению ошибки C2422:  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```
