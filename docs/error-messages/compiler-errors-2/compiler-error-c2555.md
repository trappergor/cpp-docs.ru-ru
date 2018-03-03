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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c66b464ac38a46716fbed972939feef1273ad03d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2555"></a>Ошибка компилятора C2555
«class1::function1»: переопределение виртуальной функции возвращают тип отличается и не является ковариантным «класс2::функция 2»  
  
 Виртуальная функция и производная переопределенной функции имеют идентичные списки параметров, кроме различные возвращаемые типы. Переопределенная функция в производном классе не может отличаться от виртуальной функции в базовом классе только типом возвращаемого.  
  
 Чтобы устранить эту ошибку, необходимо привести возвращаемое значение после вызова виртуальной функции.  
  
 Эта ошибка может также возникает, если компиляция выполняется с параметром/CLR.   Например эквивалентом Visual C++ следующему объявлению C#:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 является  
  
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