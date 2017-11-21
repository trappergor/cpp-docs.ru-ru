---
title: "Ошибка компилятора C2311 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2311
dev_langs: C++
helpviewer_keywords: C2311
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a7d0615f5736de4729a4247899a6b71778799226
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2311"></a>Ошибка компилятора C2311
«исключение»: перехвачено «...» в строке с номером  
  
 Обработчик "catch" для многоточия (...) должен быть последним обработчиком для исключения.  
  
 Следующий пример приводит к возникновению ошибки C2311:  
  
```  
// C2311.cpp  
// compile with: /EHsc  
#include <eh.h>  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch( ... ) {}  
   catch( int ) {}   // C2311  ellipsis handler not last catch  
}  
```