---
title: "Ошибка компилятора C2422 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2422
dev_langs: C++
helpviewer_keywords: C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 852a495406a8baf147fc53262f8fe856fce726b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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