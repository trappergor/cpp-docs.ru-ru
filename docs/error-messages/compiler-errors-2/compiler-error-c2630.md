---
title: "Ошибка компилятора C2630 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2630
dev_langs: C++
helpviewer_keywords: C2630
ms.assetid: 7a655a9c-bab4-495b-97a3-a3f34cf5369a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5a983ed18961374d999ad0a19e22be9a5316ed4c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2630"></a>Ошибка компилятора C2630
Обнаружено: «символ» должен быть список с разделителями запятыми  
  
 Символ используется в контексте, в котором требуется запятая.  
  
 В следующем примере возникает ошибка C2630:  
  
```  
// C2630.cpp  
// compile with: /c  
struct D {  
   D(int);  
};  
  
struct E {  
   E(int);  
};  
  
class C : public D, public E {  
   C();  
};  
  
C::C() : D(0) ; E(0) { }   // C2630  
C::C() : D(0), E(0) {}   // OK  
```