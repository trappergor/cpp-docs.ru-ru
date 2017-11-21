---
title: "Предупреждение (уровень 1) C4020 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4020
dev_langs: C++
helpviewer_keywords: C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4980961746f2711fcf0655dd37b5f37d8d8124e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4020"></a>Предупреждение (уровень 1) C4020 компилятора
«функция»: слишком много фактических параметров  
  
 Число фактических параметров в вызове функции превышает количество формальных параметров в прототипе или определении функции. Компилятор передает избыточные фактические параметры в соответствии с соглашением о вызовах функции.  
  
 Следующий пример приводит к возникновению ошибки C4020:  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 Возможное решение:  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```