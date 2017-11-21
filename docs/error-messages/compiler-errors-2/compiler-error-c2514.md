---
title: "Ошибка компилятора C2514 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2514
dev_langs: C++
helpviewer_keywords: C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f91dfffe27127cfbff20d7b2e67d097b65cae358
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2514"></a>Ошибка компилятора C2514
«класс»: класс не имеет конструкторов  
  
 Класс, структура или объединение не имеет конструктора со списком параметров, который соответствует параметрам, используемым для создания его экземпляра.  
  
 Класс должен быть полностью объявлен прежде, чем может быть создан.  
  
 Следующий пример приводит к возникновению ошибки C2514:  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```