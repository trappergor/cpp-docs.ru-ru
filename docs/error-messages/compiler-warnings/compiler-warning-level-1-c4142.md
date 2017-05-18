---
title: "Предупреждение (уровень 1) C4142 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 81fbb15b9589d5ddfdcc949dce24aec2a3c1716e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4142"></a>Предупреждение (уровень 1) C4142 компилятора
неопасное переопределение типа  
  
 Тип переопределяется таким образом, не влияет на созданный код.  
  
 Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
-   Функции-члена производного класса имеет другой тип возвращаемого значения из соответствующей функции-члена базового класса.  
  
-   Тип, определенный с `typedef` переопределен с помощью различный синтаксис команды.  
  
 Следующий пример приводит к возникновению ошибки C4142:  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```
