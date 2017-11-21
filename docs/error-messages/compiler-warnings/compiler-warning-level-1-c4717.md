---
title: "Предупреждение (уровень 1) C4717 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4717
dev_langs: C++
helpviewer_keywords: C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 63c67ff3bc00a62c94f82a0cf90f50ddfb9571b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4717"></a>Предупреждение компилятора (уровень 1) C4717
«функция»: рекурсия на всех путях, функция вызовет переполнение стека времени выполнения  
  
 Каждый путь через функцию содержит вызов функции. Поскольку нет возможности для выхода из функции без предварительного вызова функции себя рекурсивно, функция никогда не будет завершена.  
  
 Следующий пример приводит к возникновению ошибки C4717:  
  
```  
// C4717.cpp  
// compile with: /W1 /c  
// C4717 expected  
int func(int x) {  
   if (x > 1)  
      return func(x - 1); // recursive call  
   else {  
      int y = func(0) + 1; // recursive call  
      return y;  
   }  
}  
  
int main(){  
   func(1);  
}  
```