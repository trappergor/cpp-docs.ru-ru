---
title: "Ошибка компилятора C2571 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2571
dev_langs: C++
helpviewer_keywords: C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8bfb4f9af849efea2fa3aa8a84a57f1cfb4cd502
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2571"></a>Ошибка компилятора C2571
«функция»: виртуальная функция не может быть в объединении «объединение»  
  
 Виртуальная функция объявляется объединение. Можно объявить виртуальной функции только в классе или структуре.  Возможные решения:  
  
1.  Преобразуйте объединение в классе или структуре.  
  
2.  Не делайте функцию виртуальной.  
  
 Следующий пример приводит к возникновению ошибки C2571:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```