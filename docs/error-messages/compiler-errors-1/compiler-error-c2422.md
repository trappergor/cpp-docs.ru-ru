---
title: "Ошибка компилятора C2422 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65412576c3c1a5e6b8205652d826d0eca6d222e6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2422"></a>Ошибка компилятора C2422
Недопустимое переопределение сегмента в «операнд»  
  
 Встроенный код ассемблера неправильно использует оператор переопределения сегмента (двоеточие) в операнде.  Возможные причины:  
  
-   Регистр перед оператором не регистра сегмента.  
  
-   Регистр перед оператором не только регистром сегмента в операнде.  
  
-   Оператор переопределения сегмента появляется внутри оператора косвенного обращения (скобки).  
  
-   Выражения, следующего оператора переопределения сегмента не является непосредственным операндом или операндом памяти.  
  
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
