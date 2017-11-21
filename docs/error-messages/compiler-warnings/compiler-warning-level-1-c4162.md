---
title: "Предупреждение (уровень 1) C4162 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4162
dev_langs: C++
helpviewer_keywords: C4162
ms.assetid: 21ae3c92-501d-4689-ad7d-13753cb65eff
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e22470de248fdb5371a8d99c5150a1438abab5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4162"></a>Предупреждение (уровень 1) C4162 компилятора
«Идентификатор»: ни одна из функций с компоновкой не найдены  
  
 Функция с компоновкой объявлен, но не удается найти.  
  
 Чтобы устранить это предупреждение, компилируется в c-файла (вызвать компилятор C).  Если необходимо вызвать компилятор C++, поместите extern «C», прежде чем в объявлении функции.  
  
 Следующий пример приводит к возникновению ошибки C4162  
  
```  
// C4162.cpp  
// compile with: /c /W1  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)   // C4162  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```  
  
 Возможное решение:  
  
```  
// C4162b.cpp  
// compile with: /c  
extern "C"  
unsigned char _bittest(long* a, long b);  
#pragma intrinsic (_bittest)  
  
int main() {  
   bool bit;  
   long num = 78002;  
   bit = _bittest(&num, 5);  
}  
```