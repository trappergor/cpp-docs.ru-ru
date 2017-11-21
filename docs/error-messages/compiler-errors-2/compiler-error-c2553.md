---
title: "Ошибка компилятора C2553 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2553
dev_langs: C++
helpviewer_keywords: C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 623a09c54333ef62de7a7924cc4be02ff1b2c726
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2553"></a>Ошибка компилятора C2553
«базовая_функция»: переопределение виртуальной функции возвращают тип отличается от «переопределяющая_функция»  
  
 Функция в производном классе предпринята попытка переопределения виртуальной функции в базовом классе, но функция производного класса не имело тип значения, возвращаемого в качестве функции базового класса.  Подпись переопределяющей функции должна соответствовать сигнатуре переопределяемой функции.  
  
 Следующий пример приводит к возникновению ошибки C2553:  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```