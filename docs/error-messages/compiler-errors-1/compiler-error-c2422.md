---
title: Ошибка компилятора C2422 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 89a808e4b324b11c88be38ae7d8815bee4e232cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196351"
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