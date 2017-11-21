---
title: "Ошибка компилятора C2467 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2467
dev_langs: C++
helpviewer_keywords: C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a51321e6597bffe0dded58ffa481f054e770f9b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2467"></a>Ошибка компилятора C2467
Недопустимое объявление анонимного «пользовательского типа»  
  
 Вложенные определяемый пользователем тип был объявлен. Это ошибка при компиляции исходный код C с параметром совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) включен.  
  
 Следующий пример приводит к возникновению ошибки C2467:  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```