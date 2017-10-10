---
title: "Ошибка компилятора C2897 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2897
dev_langs:
- C++
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d3aa9ae6c79d3320104d9689f82b894cf2b76d9c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2897"></a>Ошибка компилятора C2897
деструктор или метод завершения не может быть шаблоном функции  
  
 Деструкторы и методы завершения не могут быть перегружены, поэтому объявление деструктора в качестве шаблона (приводящее к определению набора деструкторов) не допускается.  
  
 Следующий пример приводит к возникновению ошибки C2897:  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2897.  
  
```  
// C2897.cpp  
// compile with: /c  
class X {  
public:  
   template<typename T> ~X() {}   // C2897  
};  
```  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2897.  
  
```  
// C2897_b.cpp  
// compile with: /c /clr  
ref struct R2 {  
protected:  
   template<typename T> !R2(){}   // C2897 error  
};  
```
