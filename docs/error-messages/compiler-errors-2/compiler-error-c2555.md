---
title: "Ошибка компилятора C2555 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 64f66bf80e8e4b6ba7477691cb9675cec347807d
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2555"></a>Ошибка компилятора C2555
«class1::function1»: переопределение виртуальной функции возвращают тип отличается и не является ковариантным «класс2::функция 2»  
  
 Виртуальная функция и производная переопределенной функции имеют идентичные списки параметров, кроме различные возвращаемые типы. Переопределенная функция в производном классе не может отличаться от виртуальной функции в базовом классе только типом возвращаемого.  
  
 Чтобы устранить эту ошибку, необходимо привести возвращаемое значение после вызова виртуальной функции.  
  
 Эта ошибка может также возникает, если компиляция выполняется с параметром/CLR.   Например эквивалентом Visual C++ следующему объявлению C#:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 тест  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Дополнительные сведения о C2555 см. в статье базы знаний Q240862.  
  
 Следующий пример приводит к возникновению ошибки C2555:  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```
